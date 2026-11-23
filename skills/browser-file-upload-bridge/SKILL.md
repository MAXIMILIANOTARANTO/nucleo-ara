---
name: browser-file-upload-bridge
description: Puente para simular la experiencia de usuario de cargar un archivo en un input type=file desde una carpeta de imágenes alojada en GitHub. Contiene el patrón setInputFiles-style, fallbacks y la integración con full-web-interaction + browser_tab. Diseñado para EzMaker, Canva y cualquier web que acepte upload. Triggers — browser file upload, setInputFiles bridge, subir archivo desde github, simular upload usuario, file input automation.
---

# Browser File Upload Bridge

## Propósito

Simular la experiencia de un usuario que selecciona un archivo desde una carpeta local (en realidad alojada en GitHub) e inyectarlo en un input type=file de la página actual.

## Realidad técnica 2026

- Los navegadores bloquean la asignación de archivos a input type=file desde JavaScript puro por seguridad.
- Las herramientas de automatización (Playwright, Puppeteer) resuelven esto con setInputFiles / uploadFile, que operan a nivel del protocolo de automatización, no del JS de la página.
- El browser_tab actual de Grok puede o no exponer este método. El skill debe detectar y degradar con gracia.

## Flujo recomendado

1. Fuente de la imagen  
   Usar github-image-folder → obtener la imagen (ruta local en artifacts o URL raw de GitHub).

2. Intentar inyección automática
   - Localizar el input: document.querySelector('input[type="file"]') o el selector específico del sitio (input.el-upload__input en EzMaker).
   - Si el runtime de browser_tab soporta setInputFiles / file injection → usarlo.
   - Si no → pasar al fallback.

3. Fallback controlado (siempre disponible)
   - El agente prepara la imagen y el prompt.
   - Pide al usuario: “Sube esta imagen en la zona de upload (ya está lista en tu lado)”.
   - En cuanto el usuario confirma, el agente continúa con prompt + generate + captura.
   - Esto mantiene la experiencia fluida y minimiza tokens.

4. Captura del resultado
   - Después de Generate, localizar el img de resultado o el blob.
   - Guardar en artifacts y mostrar en el chat.

## Selectores comunes

| Sitio     | Selector del input          |
|-----------|-----------------------------|
| EzMaker   | input.el-upload__input     |
| Genérico  | input[type="file"]         |

## Integración

- Depende de github-image-folder para la fuente de imágenes.
- Depende de full-web-interaction + browser_tab para la ejecución.
- Usado por ezmaker-image-to-image.

## Principios de eficiencia

- Nunca gastar tokens intentando métodos imposibles más de una vez.
- Preferir el fallback rápido y confiable cuando la inyección automática no esté disponible.
- Documentar claramente qué funciona y qué no en cada runtime.
