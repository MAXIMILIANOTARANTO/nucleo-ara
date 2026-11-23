# Herramientas Image-to-3D 2026 — Referencia Rápida

## Motores Principales

### Meshy (meshy.ai)
- Mejor para: Texturas PBR, pipeline completo, personajes con rig y animación.
- Input: imagen simple o multi-imagen + texto.
- Export: GLB, FBX, OBJ, USDZ, STL, BLEND.
- Auto-rig: humanoides y cuadrúpedos.

### Tripo AI (tripo3d.ai)
- Mejor para: Velocidad + topología limpia + auto-rigging de personajes.
- Export: GLB prioritario.

### Rodin / Hyper3D
- Mejor para: Fidelidad geométrica máxima y poses T/A.
- Input: 1 a 5 imágenes.
- Export: GLB, USDZ, FBX, OBJ, STL.

### TRELLIS.2 (Microsoft) / Hunyuan3D
- Open-source / hosted de alta calidad.
- Export: GLB texturado con PBR.

## Flujo Recomendado para Valentina
1. Usar Character Design Sheet (Front + Side + Back T/A-Pose) como base.
2. Añadir 2-4 poses dinámicas "más sacando" (Look Back, Hip Pop, Mirror).
3. Generar en Meshy o Tripo con remesh + PBR.
4. Exportar GLB y validar en Blender o model-viewer.

## Checklist de Calidad GLB
- Texturas embebidas (baseColor, normal, roughness/metallic)
- Escala correcta (metros)
- Origen en el suelo / pivote centrado
- Número de triángulos razonable
- Sin materials rotos
