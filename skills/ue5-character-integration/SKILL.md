---
name: ue5-character-integration
description: Especialista en integrar personajes 3D (especialmente Valentina) en Unreal Engine 5. Cubre importación de GLB/FBX, Skeletal Mesh, materiales PBR, Physics Asset, IK Retargeter, LODs y pipeline completo desde imagen-a-3D. Conectado con imagen-a-personaje-3d-glb, valentina-valiente y github-image-folder. Triggers — unreal engine 5, ue5, integrar asset ue5, importar personaje unreal, valentina unreal, skeletal mesh ue5, pipeline ue5.
---

# UE5 Character Integration

## Propósito

Llevar un personaje 3D generado (Valentina u otros) desde el pipeline de imagen → 3D GLB/FBX hasta un asset totalmente funcional dentro de **Unreal Engine 5**.

## Flujo completo conectado (el que venimos trabajando)

```
Referencia de Valentina (Character Sheet / Lifestyle)
        ↓
github-image-folder + valentina-valiente
        ↓
ezmaker-image-to-image / Grok Imagine (opcional restyle o más sacando)
        ↓
imagen-a-personaje-3d-glb (Meshy / Tripo / Rodin → GLB o FBX + PBR)
        ↓
(Blender limpieza opcional)
        ↓
ue5-character-integration  ← este skill
        ↓
Skeletal Mesh + Material + Physics + Anim ready en UE5
```

## Formatos de entrada recomendados

| Prioridad | Formato | Motivo |
|-----------|--------|--------|
| 1 | FBX | Mejor soporte de skeleton, morphs y animaciones |
| 2 | GLB / glTF | Nativo en UE5 5.1+, bueno pero FBX más estable para characters |
| 3 | USD | Pipelines avanzados |

**Regla**: Siempre pedir al exportador de Meshy/Tripo/Rodin la opción **FBX + textures** cuando el destino sea Unreal.

## Pasos de importación (Skeletal Mesh)

1. Crear carpeta: `/Game/Characters/Valentina/`
2. Arrastrar el FBX/GLB al Content Browser
3. Configuración crítica del diálogo de importación:
   - Content Type: **Skeletal Mesh**
   - Skeleton: Create New
   - Import Mesh: ✓
   - Import Materials & Textures: ✓
   - Import Animations: ✓ (si existen)
   - Convert Scene Unit: ✓
   - Normal Import Method: Import Normals
4. Import All

## Post-importación esencial

### Skeletal Mesh
- Verificar jerarquía de huesos (pelvis → spine → neck → head, arms, legs)
- Crear **Physics Asset** (botón derecho → Create → Physics Asset)
- Ajustar cápsulas especialmente en caderas, glúteos y pecho (importante para cuerpo curvy)

### Materiales
- Crear Material Master realista (Subsurface Profile recomendado para piel)
- Material Instance por personaje
- Conectar:
  - Base Color
  - Normal
  - Roughness / Metallic (o packed)
  - Opacity / Specular si aplica

### Animación
- Crear **IK Retargeter** si se quieren usar animaciones del Mannequin o MetaHuman
- Animation Blueprint básico
- Control Rig para ajustes finos de pose o ropa

### Optimización
- Generar LODs (mínimo 3-4)
- Nanite solo si es Static Mesh de alta densidad (no recomendado para Skeletal con mucha deformación)

## Checklist rápida Valentina → UE5

- [ ] Export desde Meshy/Tripo en FBX + PBR
- [ ] Escala correcta (~172 cm)
- [ ] Skeleton limpio
- [ ] Physics Asset con colisiones de cadera/glúteo ajustadas
- [ ] Material Instance con Subsurface
- [ ] IK Retargeter configurado
- [ ] LODs generados
- [ ] Probado en nivel con iluminación realista

## Integración con el ecosistema

- **imagen-a-personaje-3d-glb**: Fuente principal del asset
- **valentina-valiente**: Mantiene coherencia de identidad y proporciones
- **github-image-folder**: Guarda las referencias multi-view usadas
- **ezmaker-image-to-image**: Restyling previo opcional

## Limitaciones y consejos

- El auto-rig de las herramientas AI rara vez es perfecto → espera un paso de limpieza en Blender o Control Rig.
- Para cuerpos muy curvy, las cápsulas de física por defecto suelen quedar cortas en glúteos → ajustar manualmente.
- Prefiere FBX sobre GLB cuando haya animación o morph targets.

## Recursos
- Documentación oficial UE5 Skeletal Mesh Import
- glTF Importer plugin (si se usa mucho GLB)
