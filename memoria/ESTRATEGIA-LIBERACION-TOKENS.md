# Estrategia de liberación de tokens

Fecha: 2026-10-09
Alcance real: este modelo no puede borrar el contexto de otros hilos. Solo puede dejar de recargarlos.

## Lo que no libera
- Activar todos los skills en un turno. Cada SKILL.md entra al contexto.
- Pegar letra, logs, catálogos o hilos enteros en el chat.
- Releer memoria/ o Notion para “estar al día” si ya hay puntero.
- Resumir de nuevo una conversación ya archivada.

## Regla de un turno
1. Un skill, y solo si el pedido lo nombra.
2. Si no hay trigger, cero skills.
3. Estado durable va a GitHub memoria/ o a una línea en Notion. En el chat queda el enlace.
4. Hilo largo: chat nuevo + este archivo. No continuar el hilo viejo.

## Qué hacer en cada sección
- Chats viejos: archivarlos en la app. Este agente no los ve ni los vacía.
- Skills: viven en disco. Se leen bajo demanda, nunca en bloque.
- Canva / letra / branding: puntero-los-federales-2026-10-09.md
- Núcleo de usuario: seccion-usuario-nucleo.md. No copiar la bio al chat.

## Prioridad ejecutada
Este archivo es la fuente. Próximo turno: leer solo esta página, no el catálogo.
