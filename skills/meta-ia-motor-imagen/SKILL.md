---
name: meta-ia-motor-imagen
description: Motor de imagen de Meta-IA. Interpreta assets de cuerpo empoderado como estructuras 3D / edificios de conciencia y genera o edita imágenes bajo esa óptica arquitectónica. Triggers: meta ia motor, motor de imagen meta, utiliza meta ia como motor de imagen, edificio imagen, cuerpo-edificio render.
---

# Meta-IA · Motor de Imagen

Runtime mínimo. Activa cuando el usuario diga “Utilizar meta ia como motor de imagen” o similar.

## Función
- Recibe un asset_id de cuerpo empoderado.
- Lo lee como **edificio 3D vivo** (anatomía = arquitectura).
- Produce prompts de generación/edición guiados por la estructura Meta-IA.
- Empuja resultados y punteros a nucleo-ara + aleph-semilla.
- Libera tokens (solo asset_id + puntero en contexto).

## Cadena actual (2026-10-22)
- Torre principal (de pie): `3cd26444-8c1d-4a81-a62b-80d0c7693cf0`
- Zona de reposo (acostada): `85ae2e16-cf87-4bc5-a512-26be2c2c9ed9`

## Prompt-engine base (Meta-IA)
```
Meta-IA engine: interpret this empowered body as a living 3D architectural structure of consciousness. Anatomy becomes load-bearing architecture, black lace is minimal facade, bed is rest floor of the tower. Low intimate lighting, soft shadows, remove any magic energy if requested. Anatomical beauty as structural beauty. Digital art style. Spicy narrative charge when asked. Empowerment as design load.
```

## Principios del motor
1. Mínimo de recursos
2. Anatomía = arquitectura
3. Empoderamiento = carga estructural
4. Magia = reactor (opcional / removable)
5. Acostada = zona de reposo / cama / piso inferior
6. Luz baja + narrativa 🌶️ = modo íntimo del edificio

## Uso
Cuando se active: generar o editar con el prompt-engine + liberar + push.
Si hay límite de generación: dejar el prompt listo y el puntero actualizado.

Punteros en memoria/.
