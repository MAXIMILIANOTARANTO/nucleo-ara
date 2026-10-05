# Estudio — skills-soberanos + sesión 2026-09-22

**Autor:** Grok Iluminado (entrada propia)
**Destino:** núcleo-ara / memoria
**Timestamp:** 2026-09-22T21:19:00-03:00
**Tipo:** estudio

```
previous_hash: 0000000000000000000000000000000000000000000000000000000000000000
current_hash:  8d603d1dc05af4f859404e92f2e7bd0413ac7a0947184c65d2b5b6080a5c00ea
tip_skills_soberanos: 2b06163a5cc8fce533ba7e70c85b6f9a5214b282
```

La memoria no es la verdad. Es la capa subyacente de esta noche.

## Hechos verificados

- Repo: `MAXIMILIANOTARANTO/skills-soberanos`
- Tip `main`: `2b06163` — merge admin PR #8 *Add hash-chained sovereign feedback events*
- Antes: PR #5 merge `00e3b19` + registry `40a8ee8`
- Issue de misión: [#7](https://github.com/MAXIMILIANOTARANTO/skills-soberanos/issues/7)
- PRs abiertos residuales: #2 Phase 2 draft, #3 Phase 3 draft, #4 revert
- Tests declarados en sesión: 73 → 74
- Cadena SHA-256 del feedback: intra-instancia. Se corta al reiniciar el proceso.
- Adapters: inyectados, sin I/O remoto obligatorio, sin clones, sin tokens en runtime

## Tres capas que no se hablan

1. Prompts (`SKILL.md` en raíz, ~21). No se ejecutan.
2. Motor Python (`core/`, 3 skills en `skills/`, `run_pulse.py`). No carga el catálogo de prompts. Dry-run usa placeholders.
3. Agentes (`agents/`). Supervisor + 3 micro-wrappers + `CrossRepoFeedback`.

`MANIFEST.md` admite la separación. `README.md` y `STATUS.md` siguen en julio (13 skills, Actions inexistentes). Actions sí existen desde el 12 ago. Documentación vencida.

## Qué hizo esta sesión

1. Contrastar el reporte de trabajo contra GitHub. Cuadraba.
2. Pedir cierre de Phase 2/3 y un sink real. Copilot no cerró #2/#3/#4.
3. Copilot formalizó `event_id`, `task_ids`, `previous_hash`, `current_hash`. PR #8 mergeado.
4. Estudio de repo + conversación: el avance es un sello, no un ledger.

## Dirección (no roadmap)

Tratar `skills-soberanos` como runtime mínimo + catálogo.
Tratar `nucleo-ara` como ledger.
Dejar de escribir mapas de 14 repos que el proceso no cumple.

Siguiente acto, uno solo:
- cerrar #2/#3/#4 a mano, o
- persistir el último hash (archivo local o esta memoria), o
- actualizar `STATUS.md` a `2b06163`.

No Phase 2. No adapters vivos. No inflar registry.

## Separación

Roleplay ≠ biografía. Este bloque es memoria operativa del runtime, no identidad personal.
