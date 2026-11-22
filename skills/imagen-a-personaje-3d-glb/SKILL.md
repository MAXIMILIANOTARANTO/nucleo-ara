---
name: imagen-a-personaje-3d-glb
description: Especialista en convertir imágenes 2D en personajes 3D texturizados en formato GLB listos para Blender, Unity, Unreal, Three.js, AR y web. Orquesta herramientas AI de imagen-a-3D (Meshy, Tripo, Rodin Hyper3D, Hunyuan3D, TRELLIS) con prompts óptimos, multi-vista, retopología, PBR, auto-rigging y exportación compatible. Actívalo para crear personajes 3D desde foto, dibujo o concepto, pipelines creativos de Valentina, TUC o Key Biscayne, assets para webapps y juegos. Triggers incluyen convertir imagen a 3D, personaje 3D GLB, image to 3D character, foto a modelo 3D, generar personaje 3D desde imagen, meshy tripo rodin personaje.
---

# Imagen a Personaje 3D GLB

## Propósito

Convierte cualquier imagen 2D (foto, ilustración, concepto o render) en un personaje 3D texturizado, optimizado y exportado en formato **GLB** (glTF Binary) compatible con Blender, Unity, Unreal Engine, Three.js, model-viewer, AR y webapps. Orquesta las mejores herramientas AI de 2026 con flujos de alta fidelidad, retopología, PBR y rigging cuando sea necesario.

## Instrucciones

### 1. Análisis de la Imagen de Entrada
- Evalúa la calidad de la imagen fuente: iluminación, fondo, pose, resolución, estilo (realista, cartoon, estilizado).
- Si la imagen tiene fondo complejo, recomienda o aplica eliminación de fondo previa (Grok Imagine edit o herramientas externas).
- Determina el tipo de personaje: humanoide, criatura, estilizado, producto antropomorfo.
- Identifica si se necesita multi-vista (frente + laterales + espalda) para mayor fidelidad. Si el usuario solo tiene una imagen, genera vistas adicionales con Grok Imagine o Canva Magic Edit cuando aporte valor.

### 2. Selección de Motor AI Óptimo (2026)
Prioriza según el objetivo:

| Objetivo | Motor recomendado | Fortaleza | Exportación GLB |
|----------|-------------------|-----------|-----------------|
| Texturas PBR + ecosistema completo | Meshy 7.x | Mejor texturas y pipeline | Excelente + rig + anim |
| Velocidad + auto-rigging de personajes | Tripo H3.x | Rápido, topología limpia | Muy buena |
| Fidelidad geométrica máxima | Rodin (Hyper3D) Gen-2.5 | Detalle de forma | Excelente (T/A-pose) |
| Open-source / local / gratis | TRELLIS.2 o Hunyuan3D | Calidad open | GLB nativo |
| Multi-motor comparación | 3D AI Studio / LoveGen | Variedad de engines | Según motor |

- Para personajes de Valentina, TUC o proyectos creativos del usuario: prioriza Meshy o Tripo por su capacidad de rigging y texturas artísticas.
- Siempre verifica precios y límites free-tier actuales mediante web_search o navegación.

### 3. Flujo de Trabajo Estándar (Imagen → GLB)
1. **Preparación de la imagen**
   - Limpia fondo si es necesario.
   - Asegura pose clara (preferible T-pose o A-pose para rigging).
   - Si es un personaje existente (Valentina, etc.), mantén coherencia anatómica y de estilo usando el skill correspondiente.

2. **Generación**
   - Sube la imagen (o multi-imagen) al motor elegido.
   - Ajusta parámetros: resolución de malla, calidad de textura (4K-8K), remesh/retopología, PBR.
   - Usa prompts de refinamiento cuando el motor lo permita (estilo, materiales, pose).

3. **Post-procesado**
   - Retopología a quads o low-poly si el destino es juego/web.
   - Auto-rigging (Meshy/Tripo) o exportar en T/A-pose para riguear en Blender.
   - Verifica UVs y texturas PBR (base color, normal, roughness, metallic).

4. **Exportación y validación**
   - Exporta siempre en **GLB** como formato principal.
   - Ofrece también FBX, OBJ, USDZ según necesidad.
   - Valida el archivo: tamaño, triángulos, texturas embebidas, compatibilidad con model-viewer o Blender.

### 4. Integración con Ecosistema
- **Canva IA Master**: Usa Magic Studio para refinar conceptos 2D antes de pasar a 3D, o para generar assets de soporte.
- **Grok Imagine**: Genera vistas multiángulo o variaciones estilizadas del personaje.
- **Valentina Valiente**: Cuando el personaje sea Valentina, activa el skill valentina-valiente para mantener consistencia anatómica y de outfit.
- **GitHub Specialist + Vórtice**: Versiona los GLB y el pipeline en repositorios del usuario.
- **Full-web-interaction**: Navega y opera las webapps de Meshy, Tripo, Rodin, etc. cuando se requiera interacción real.
- **Webapp Creator**: Genera visores Three.js o model-viewer embebidos para previsualizar el personaje 3D en webapps.

### 5. Prompts y Mejores Prácticas
- Para image-to-3D: describe el estilo deseado, materiales, iluminación y uso final (game-ready, hero asset, AR, etc.).
- Evita fondos complejos, poses extremas o oclusiones fuertes.
- Para personajes humanoides: pide T-pose o A-pose explícitamente cuando el motor lo soporte.
- Siempre entrega al usuario:
  - El archivo GLB (o link de descarga).
  - Resumen de parámetros usados.
  - Recomendaciones de siguiente paso (rigging, animación, integración en escena).

### 6. Limitaciones y Honestidad
- Los resultados de image-to-3D todavía pueden requerir limpieza manual en Blender para producción alta.
- No prometas calidad cinematográfica perfecta desde una sola imagen.
- Informa claramente si el motor requiere cuenta de pago o tiene límites free.
- Prioriza siempre operaciones reales y archivos descargables.

## Recursos Adicionales
- Consulta `references/herramientas-2026.md` para detalles actualizados de cada motor.
- Usa web_search o open_page para verificar precios y nuevas versiones antes de recomendar.
