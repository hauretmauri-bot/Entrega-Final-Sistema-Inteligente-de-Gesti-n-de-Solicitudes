Entrega Final: Sistema Inteligente de Gestión de Solicitudes (n8n + Gemini)

Información del Proyecto
- Autor: Mauricio Hauret
- Orquestador: n8n
- Base de Datos: Google Sheets
- Motor de IA: Google Gemini (Gemini 2.5 Flash-Lite / 3.5 Flash-Lite)
- Comunicación: Gmail

---

Enlaces Obligatorios de Entrega
- Documento Completo (PDF): [Entrega Final_ Sistema Inteligente De Gestión de Solicitudes.pdf](https://github.com/user-attachments/files/32362068/Entrega.Final_.Sistema.Inteligente.De.Gestion.de.Solicitudes.pdf)
- Flujo Técnico (.json): [Proyecto Final - Automatización IA (2).json](https://github.com/user-attachments/files/32359185/Proyecto.Final.-.Automatizacion.IA.2.json)
- Dashboard de Control & Base de Datos (Shared View): https://docs.google.com/spreadsheets/d/1f7UGJxnAArrakg9J2KwLqHXPuFB94Jhd7cgGQIIm_x0/edit?usp=sharing
- Video Demo (3 min): [Enlace a Loom/YouTube](PEGA_AQUI_TU_LINK_DEL_VIDEO)

---

Arquitectura del Sistema:

El flujo captura solicitudes mediante formulario, procesa el texto con Gemini para clasificar prioridad/categoría, actualiza Google Sheets, solicita revisión humana (HITL) vía correo y ejecuta la notificación final al usuario tras la aprobación o rechazo.

Resiliencia y Manejo de Errores:

Cuenta con un nodo "Error Trigger" independiente que intercepta fallos de API o tiempos de espera agotados, guardando el registro técnico en la pestaña "Ejecuciones" de Google Sheets.

Aclaraciones:
Aunque para fines prácticos y de prueba de este prototipo se utilizó un formulario nativo de n8n (n8n Form Trigger), la arquitectura del sistema es totalmente flexible. El canal de entrada puede ser reemplazado fácilmente por herramientas de comunicación interna empresarial como Slack (mediante Slash Commands o un bot de canal), Microsoft Teams, un Formulario de Google / Typeform, o un Webhook personalizado conectado al sistema de soporte de la empresa, sin alterar la lógica de procesamiento con IA ni el control humano del flujo.
