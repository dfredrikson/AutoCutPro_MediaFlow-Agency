# Backlog Ágil: Historias de Usuario

A continuación se detallan las funcionalidades requeridas para el ciclo de desarrollo actual de AutoCut Pro, estructuradas bajo formato ágil y con sus respectivos criterios de aceptación vinculados al modelo de datos.

### Historia de Usuario 1: Parametrización del Algoritmo
*   **Historia:** Como editor de MediaFlow Agency, quiero configurar el nivel de agresividad del VAD y los tiempos de padding, para ajustar la precisión del corte automático según el tipo de video que estoy procesando.
*   **Criterios de Aceptación:**
    1. El sistema debe permitir ingresar un valor de `VAD_Agresiv` numérico entero entre 0 y 3 exclusivamente.
    2. El sistema debe guardar el margen de seguridad (`Padding`) en milisegundos, aceptando únicamente valores enteros mayores o iguales a 0.
    3. Al procesar, la base de datos debe generar un `ID_Config` único vinculado al `ID_Proyecto` mediante llave foránea (FK).

### Historia de Usuario 2: Importación y Validación del Entorno
*   **Historia:** Como usuario, quiero importar mi archivo FCPXML y el video original, para que el sistema recupere los datos del proyecto y ejecute el procesamiento de forma local.
*   **Criterios de Aceptación:**
    1. El sistema debe validar que el archivo cargado tenga obligatoriamente la extensión `.fcpxml`.
    2. El sistema debe verificar los requerimientos mínimos de hardware, confirmando la ejecución sobre un procesador Apple Silicon (arquitectura ARM) y macOS 14 o superior, abortando la importación si no se cumple.
    3. El sistema debe registrar en la base de datos la `RutaXML`, el `FPS_Proyecto` y detectar si el campo `PistasAudio` es mayor a 0 antes de habilitar el botón de procesar.

### Historia de Usuario 3: Validación de Permisos de Uso y Exportación
*   **Historia:** Como usuario del software, quiero que el sistema verifique mi estado de suscripción al iniciar la aplicación, para habilitar el uso del programa y la posterior exportación del FCPXML.
*   **Criterios de Aceptación:**
    1. El sistema debe leer el campo `Email` de la base de datos local y validar su formato mediante expresión regular.
    2. El software debe consultar el atributo booleano `Activa` contra el servidor. Si el valor es Verdadero (V), se inicia el programa normalmente; si es Falso (F), la interfaz se bloquea y lanza una alerta de "Suscripción Vencida".
