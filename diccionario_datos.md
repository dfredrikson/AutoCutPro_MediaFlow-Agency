# Diccionario de Datos - AutoCut Pro

Este documento define las cuatro entidades críticas del sistema para el procesamiento local de archivos y la gestión de licencias.

### Entidad: Proyecto_FCPXML
| Campo | Tipo | Long | Descripción | Llave | Validación |
| :--- | :--- | :--- | :--- | :--- | :--- |
| `ID_Proyecto` | Integer | 10 | Identificador único del proyecto importado | PK | |
| `RutaXML` | String | 255 | Ubicación local del archivo XML | | Formato: .fcpxml |
| `FPS_Proyecto` | Float | 5 | Fotogramas por segundo del proyecto | | Ej: 24, 30, 60 |
| `PistasAudio` | Integer | 2 | Cantidad de pistas de audio detectadas | | > 0 |

### Entidad: Configuracion_Algoritmo
| Campo | Tipo | Long | Descripción | Llave | Validación |
| :--- | :--- | :--- | :--- | :--- | :--- |
| `ID_Config` | Integer | 10 | Código de la configuración guardada | PK | |
| `ID_Proyecto` | Integer | 10 | Proyecto asociado a la configuración | FK | |
| `VAD_Agresiv` | Integer | 1 | Nivel de sensibilidad para detectar voz | | Rango: 0 a 3 |
| `MinSilencio` | Integer | 5 | Duración mínima a cortar en milisegundos | | > 0 |
| `Padding` | Integer | 4 | Margen antes y después del corte en ms | | >= 0 |

### Entidad: Archivo_Crudo
| Campo | Tipo | Long | Descripción | Llave | Validación |
| :--- | :--- | :--- | :--- | :--- | :--- |
| `ID_Archivo` | Integer | 10 | Identificador único del video procesado | PK | |
| `ID_Proyecto` | Integer | 10 | Proyecto al que pertenece el archivo | FK | |
| `RutaVideo` | String | 255 | Directorio local del medio audiovisual | | Formato: .mp4, .mov |
| `DuracionSeg` | Integer | 8 | Tiempo total del archivo original en seg. | | > 0 |

### Entidad: Licencia_Usuario
| Campo | Tipo | Long | Descripción | Llave | Validación |
| :--- | :--- | :--- | :--- | :--- | :--- |
| `Email` | String | 50 | Correo electrónico de cuenta del usuario | PK | email@dominio.com |
| `InicioTrial` | Date | | Fecha de inicio del periodo de prueba | | DD/MM/AAAA |
| `Activa` | Boolean | | Estado vigente de la suscripción | | V: Vigente, F: Vencida |
| `FechaCompra` | Date | | Fecha de adquisición del software | | DD/MM/AAAA |