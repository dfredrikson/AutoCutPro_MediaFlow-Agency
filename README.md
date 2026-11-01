# AutoCut Pro - MediaFlow Agency

## 📝 Descripción del Sistema
**AutoCut Pro** es una herramienta de software de escritorio nativa para macOS, diseñada para optimizar los flujos de trabajo de edición de video en MediaFlow Agency. El sistema procesa de forma local (*offline-first*) archivos multimedia originales junto con líneas de tiempo exportadas desde Final Cut Pro (.fcpxml). Mediante un algoritmo de Detección de Actividad de Voz (VAD), identifica y elimina silencios automáticamente, generando un nuevo archivo XML con los cortes precisos para ser reimportado al editor, garantizando la máxima privacidad de los datos del cliente.

**Requisitos del Sistema:** macOS 14+ / Procesadores Apple Silicon (ARM).

## 👥 Equipo de Desarrollo (Estructura Organizacional)
*   **Daniel Fredrikson** - Líder de Proyecto / Arquitecto Backend
*   **Nicole Figueroa** - Desarrolladora Frontend / UI
*   **Ariel Aranda** - Analista de Calidad (QA)
*   *(Staff Externo)* - Asesoría Legal y Privacidad de Datos

## 📊 Tablero de Gestión Ágil
El seguimiento de las Historias de Usuario, tareas y control de estados (Todo, In Progress, Done) se gestiona a través de nuestro entorno colaborativo:
👉 **https://github.com/users/dfredrikson/projects/2**

## ⚙️ Indicadores de Control y Estándares de Desempeño
Para la auditoría técnica y el aseguramiento de la calidad (QA) del sistema, se establecen los siguientes parámetros de control:
1.  **Latencia de Procesamiento:** El sistema debe analizar y procesar 1 hora de video crudo (1080p, 60fps) en un tiempo máximo de **12 minutos** operando sobre hardware Apple Silicon.
2.  **Precisión del Algoritmo (VAD):** El margen de error en la detección de silencios no debe superar el **5%** (falsos positivos/negativos) en condiciones de ruido ambiente normal.
3.  **Integridad de Exportación:** El archivo `.fcpxml` resultante debe registrar una tasa de fallo de importación a Final Cut Pro del **0%**, manteniendo intactas las pistas de audio originales no procesadas.

## 🤖 Declaración de Transparencia y Uso Crítico de IA
En cumplimiento con las pautas de la asignatura Organización Empresarial, se declara el uso de asistentes de Inteligencia Artificial Generativa bajo un enfoque de competencia profesional y revisión crítica:
*   **Propósito Específico:** Se utilizó la IA como soporte para la estructuración sintáctica del diccionario de datos, la validación teórica de los roles de Staff en el organigrama y la redacción formal de las Historias de Usuario bajo el estándar ágil (Como... Quiero... Para...).
*   **Corrección Humana e Intervención Crítica:** Los *prompts* iniciales fueron estrictamente delimitados al contexto tecnológico del software (macOS, FCPXML, local-first). Los resultados generados por la IA fueron auditados por el equipo, corrigiendo alucinaciones estructurales (ej. unificando tareas separadas en un modelo de *Issues* colaborativas) e inyectando lógica de negocio específica (como la validación temprana de licencias para optimizar recursos). La responsabilidad intelectual e integridad técnica del código y la documentación recae 100% en los autores humanos.
