# Checkpoint 4 – Automatización Multiagente con n8n

## Descripción
Sistema de gestión de consultas de clientes mediante una arquitectura multiagente desarrollada en n8n, con integración de Gmail, HubSpot, Airtable, Google Gemini y Slack.

## Arquitectura
- **Manager:** coordina el flujo, recupera contexto y decide qué Worker ejecutar.
- **Worker 1 – Extractor:** identifica datos del cliente.
- **Worker 2 – Redactor:** genera respuestas considerando el contexto disponible.

## Funcionamiento
1. Gmail recibe una consulta.
2. Se filtran correos automáticos y se valida el email.
3. HubSpot busca el contacto y lo crea si no existe.
4. El Manager recupera la memoria de Airtable y clasifica la consulta.
5. El Worker correspondiente procesa el mensaje.
6. Gmail crea un borrador, sin enviarlo automáticamente.
7. Slack notifica que el borrador está pendiente de revisión humana.

## Seguridad y control
- Filtro de respuestas automáticas y remitentes no-reply.
- Validación del correo electrónico.
- Verificación de contactos existentes para evitar duplicados.
- Revisión humana obligatoria antes del envío de respuestas.

## Archivos
- `Checkpoint4_Manager_Integraciones.json`
- `Worker_1_Extractor.json`
- `Worker_2_Redactor.json`

## Pruebas realizadas
- Bloqueo de correos automáticos.
- Validación de email.
- Búsqueda de contactos existentes en HubSpot.
- Creación de borradores en Gmail.
- Notificación en Slack.

## Consideraciones
Los workflows requieren configurar credenciales propias y vincular los subworkflows correspondientes dentro de n8n.# n8n-checkpoints-adv
