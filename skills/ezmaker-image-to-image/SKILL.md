---
name: ezmaker-image-to-image
description: Especialista operativo en EzMaker AI Image-to-Image (https://ezmaker.ai/image-to-image/). Ejecuta el flujo completo real en el navegador — subir imagen de referencia, escribir prompt, seleccionar aspect ratio, generar, descargar y mostrar el resultado en el chat. Usa full-web-interaction + browser_tab. Ideal para Valentina, clothes changer, restyle y pipelines creativos. Triggers — ezmaker, image to image ezmaker, usa ezmaker, transformar imagen con ezmaker, ejecuta ezmaker, clothes changer ezmaker.
---

# EzMaker Image-to-Image — Operativo Completo

## Propósito

Ejecutar de forma real y completa el flujo de **EzMaker AI Image-to-Image** desde este chat:

1. Subir una imagen de referencia
2. Escribir el prompt optimizado
3. Seleccionar aspect ratio
4. Pulsar Generate
5. Esperar el resultado
6. Descargar la imagen generada
7. Mostrarla aquí en el chat

Todo usando `browser_tab` + `full-web-interaction`.

## Selectores Clave (actualizados 2026-11-23)

- **File input**: `input.el-upload__input` (accept image/jpeg,image/png,image/webp)
- **Prompt textarea**: `textarea.el-textarea__inner`
- **Aspect ratio items**: `.ratio-item` (textos 1:1, 3:2, 2:3, 9:16, 16:9, 3:4, 4:3)
- **Generate button**: `button.generate-btn` o `button.wordpress-demo-generate`

## Flujo Operativo Completo

### 1. Preparar imagen de referencia
- Usar la imagen más reciente del chat (attachments) o la que indique el usuario.
- Ruta típica: `/home/workdir/attachments/...`

### 2. Abrir el editor
Usar `browser_tab` con:
```
url: "https://ezmaker.ai/image-to-image/"
```
Esperar carga completa del editor (zona "Image Upload" visible).

### 3. Subir la imagen
- Localizar `input.el-upload__input`
- Usar la capacidad del browser tool para adjuntar el archivo local al input (setInputFiles o equivalente).
- Si no es posible setear directamente, hacer click en la zona de upload y manejar el diálogo.

### 4. Escribir el prompt
```js
const ta = document.querySelector('textarea.el-textarea__inner');
ta.value = PROMPT;
ta.dispatchEvent(new Event('input', { bubbles: true }));
ta.dispatchEvent(new Event('change', { bubbles: true }));
```

**Prompt Identity Lock (Valentina):**
```
Keep the exact same face, dense freckles, intense blue eyes, long dark wavy hair, body proportions and pose of the woman. 
[CAMBIO].
Photorealistic, highly detailed skin and fabric, preserve original lighting.
```

### 5. Seleccionar Aspect Ratio
Click en el `.ratio-item` deseado (recomendado 2:3 o 9:16 para cuerpo completo).

### 6. Generar
```js
document.querySelector('button.generate-btn, button.wordpress-demo-generate').click();
```

### 7. Esperar y capturar
- Esperar a que el panel de resultado muestre la nueva imagen.
- Extraer la URL del `<img>` generado o descargar el blob.
- Guardar en `/home/workdir/artifacts/ezmaker-result-XXXX.jpg`

### 8. Mostrar en el chat
Usar `view_image` o el mecanismo de render de archivos para que el usuario vea el resultado inmediatamente.

## Integración

- **valentina-valiente**: Siempre aplicar Identity Lock + modo Más Sacando cuando se pida.
- **full-web-interaction**: Skill dependiente — este es el motor de ejecución real.
- **imagen-a-personaje-3d-glb**: Usar EzMaker para generar multi-view limpios antes de 3D.
- **github-specialist**: Guardar prompts exitosos.

## Limitaciones

- Dependiente de que el browser tool soporte file upload desde el sandbox.
- Los selectores pueden cambiar — re-inspeccionar si falla.
- No hay historial en EzMaker → descargar siempre.

## Recursos
- URL: https://ezmaker.ai/image-to-image/
- Selectores verificados: 2026-11-23
