# Herramientas Image-to-3D 2026 — Referencia Rápida

## Motores Principales

### Meshy (meshy.ai)
- **Mejor para**: Texturas PBR, pipeline completo, personajes con rig y animación.
- Versión actual aproximada: Meshy 7.x
- Input: imagen simple o multi-imagen + texto.
- Export: GLB, FBX, OBJ, USDZ, STL, BLEND.
- Auto-rig: humanoides y cuadrúpedos.
- Notas: Excelente ecosistema y plugins para Blender/Unity/Unreal.

### Tripo AI (tripo3d.ai)
- **Mejor para**: Velocidad + topología limpia + auto-rigging de personajes.
- Input: imagen / multi-vista / texto.
- Export: GLB prioritario.
- Notas: Muy bueno para criaturas y personajes con rig rápido.

### Rodin / Hyper3D (hyper3d.ai o rodin)
- **Mejor para**: Fidelidad geométrica máxima y poses T/A.
- Input: 1 a 5 imágenes.
- Export: GLB, USDZ, FBX, OBJ, STL.
- Notas: Ideal cuando la forma importa más que la textura inicial. Fácil de riguear después.

### TRELLIS.2 (Microsoft Research)
- **Mejor para**: Open-source de alta calidad.
- Requiere GPU local (recomendado ≥24GB VRAM) o espacios Hugging Face.
- Export: GLB texturado con PBR.
- Licencia: MIT (verificar versión actual).

### Hunyuan3D (Tencent)
- **Mejor para**: Alternativa open/hosted con buena síntesis de texturas.
- Export: GLB / OBJ.
- Buena opción free o de bajo costo.

### Otros relevantes
- **3D AI Studio / LoveGen**: Multi-motor en una sola interfaz (comparar varios engines).
- **Luma Genie**: Rápido y free para conceptos.
- **HI3D / NovaGen3D / Sculptor**: Orientados a Three.js y web.

## Flujo Recomendado para Personajes

1. Imagen limpia (fondo simple o eliminado).
2. Generar en Meshy o Tripo con opción de remesh + PBR.
3. Si se necesita rig: usar auto-rig del motor o exportar en T-pose a Blender.
4. Optimizar polycount según destino (web/AR = low-poly, hero = mid/high).
5. Empaquetar en GLB con texturas embebidas.

## Checklist de Calidad GLB

- [ ] Texturas embebidas (baseColor, normal, roughness/metallic)
- [ ] Escala correcta (metros)
- [ ] Origen en el suelo / pivote centrado
- [ ] Número de triángulos razonable para el uso
- [ ] Sin materials rotos al importar en Blender o model-viewer
- [ ] Nombre de nodos limpio si se va a animar

## Integración Web (Three.js / model-viewer)

```html
<!-- Ejemplo mínimo model-viewer -->
<script type="module" src="https://ajax.googleapis.com/ajax/libs/model-viewer/3.3.0/model-viewer.min.js"></script>
<model-viewer src="personaje.glb" alt="Personaje 3D" auto-rotate camera-controls></model-viewer>
```

Para proyectos del ecosistema (Valentina, TUC, webapps), genera siempre un visor embebible listo.
