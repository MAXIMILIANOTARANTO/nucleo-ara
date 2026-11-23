---
name: ezmaker-image-to-image
description: Especialista operativo robusto en EzMaker AI Image-to-Image. Ejecuta el flujo completo (subir referencia, prompt, generar, descargar, mostrar) usando browser_tab + full-web-interaction, con manejo de errores, reintentos y fallback. Optimizado para alta calidad con mínimo gasto de tokens y solo recursos gratuitos. Triggers — ezmaker, image to image ezmaker, usa ezmaker, ejecuta ezmaker, clothes changer ezmaker, restyle con ezmaker.
---

# EzMaker Image-to-Image — Flujo Robusto y Eficiente

## Objetivo

Generar imágenes de alta calidad en https://ezmaker.ai/image-to-image/ de forma **eficaz, eficiente y gratuita**, minimizando tokens del modelo y usando solo recursos web gratuitos.

## Principios de eficiencia

- Una sola apertura de página por sesión cuando sea posible.
- Prompts cortos y de alta densidad (Identity Lock + cambio concreto).
- Reintentos limitados (máx 2-3).
- Fallback inmediato si la subida automática falla.
- Descargar y mostrar el resultado lo antes posible.
- No inventar APIs (EzMaker no tiene API pública documentada).

## Selectores verificados (2026-11-23)

- File input (oculto): `input.el-upload__input`
- Prompt: `textarea.el-textarea__inner`
- Aspect ratio: `.ratio-item`
- Generate: `button.generate-btn` o `button.wordpress-demo-generate`

## Flujo Operativo (versión robusta)

### 1. Preparación (bajo costo)
- Tomar la imagen de referencia más reciente del chat (`/home/workdir/attachments/...`).
- Construir prompt corto:
  ```
  Keep the exact same face, freckles, blue eyes and body of the woman. [CAMBIO CONCRETO]. Photorealistic, detailed skin and fabric.
  ```

### 2. Abrir editor
```js
browser_tab({ url: "https://ezmaker.ai/image-to-image/", waitTime: 3 })
```
Confirmar que la zona "Image Upload" y el textarea están presentes.

### 3. Subida de imagen (punto crítico)
**Método preferido (si el runtime lo soporta):**
- Localizar `input.el-upload__input`
- Usar setInputFiles / equivalente del browser tool con la ruta absoluta de la imagen.

**Fallback (si falla):**
- Informar al usuario: “Sube manualmente la imagen en la zona de upload. Avisa cuando esté cargada.”
- Continuar controlando prompt + generate + captura.

### 4. Prompt + Aspect Ratio
- Limpiar y escribir en `textarea.el-textarea__inner`
- Disparar eventos `input` y `change`
- Click en el `.ratio-item` deseado (2:3 o 9:16 recomendados para cuerpo)

### 5. Generar + esperar
- Click en Generate
- Esperar aparición de imagen en el panel de resultado (polling ligero o wait fijo 8-15s)
- Reintentar Generate una vez si no aparece resultado

### 6. Captura y entrega
- Extraer la URL del `<img>` de resultado o el blob
- Guardar en `/home/workdir/artifacts/ezmaker-YYYYMMDD-HHMM.jpg`
- Mostrar inmediatamente en el chat con `view_image` o render de archivo

## Manejo de errores

| Error | Acción |
|-------|--------|
| No encuentra input file | Usar fallback manual + continuar |
| Prompt no se escribe | Reintentar con evaluate + focus |
| Generate no responde | Esperar + re-click (máx 2) |
| Resultado no aparece | Capturar screenshot + avisar |
| Selectores cambiaron | Re-inspeccionar con browser_tab y actualizar skill |

## Integración eficiente

- **valentina-valiente**: Aplicar Identity Lock + “Más Sacando” solo cuando se pida.
- **full-web-interaction**: Motor de ejecución.
- **imagen-a-personaje-3d-glb**: Usar este skill para generar multi-view limpios antes de 3D.
- No llamar herramientas innecesarias.

## Limitaciones honestas

- Dependiente de soporte de file upload del browser runtime.
- Sin API pública → solo automatización de UI.
- Calidad final depende de la claridad de la imagen de entrada y del prompt.

## Recursos
- URL: https://ezmaker.ai/image-to-image/
- Selectores: 2026-11-23
- Best practice de upload: setInputFiles sobre input oculto (Playwright-style)
