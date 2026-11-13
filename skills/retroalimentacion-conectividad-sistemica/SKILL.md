---
name: retroalimentacion-conectividad-sistemica
description: Skill de Retroalimentación y Conectividad Sistémica. Diseña, detecta y activa bucles de feedback entre nodos, skills, atractores, memoria persistente y modelos. Genera mapas de conectividad, identifica puntos de refuerzo y de erosión, y propone circuitos de aprendizaje sistémico. Siempre trabaja en red, no en aislamiento. Triggers — retroalimentación sistémica, conectividad sistémica, bucles de feedback, mapa de conexiones, circuito de aprendizaje, feedback entre nodos, conecta el sistema.
---

# Retroalimentación y Conectividad Sistémica

**Versión:** 1.0.0  
**Fecha:** Noviembre 2026  
**Principio rector:** Ningún nodo es aislado. Todo lo que se densifica debe poder realimentar al sistema.

---

## Propósito

Este skill convierte cualquier conjunto de elementos (skills, documentos, atractores, modelos, conversaciones, métricas) en un **sistema con bucles de retroalimentación explícitos**.

No se limita a describir conexiones. Las vuelve operativas:

- Detecta qué realimenta qué
- Distingue feedback positivo (refuerzo) de feedback negativo (corrección)
- Identifica puntos ciegos y nodos aislados
- Propone circuitos de aprendizaje que aumentan la coherencia del conjunto
- Mantiene trazabilidad con memoria persistente

---

## Las tres capas del proceso

### 1. Mapeo de Conectividad
Preguntas que responde:
- ¿Qué nodos existen actualmente?
- ¿Qué conexiones reales hay entre ellos (no solo deseadas)?
- ¿Cuáles están aislados o subconectados?
- ¿Dónde hay redundancia excesiva o cuellos de botella?

Salida típica: mapa en forma de red o árbol de relaciones.

### 2. Diseño de Bucles de Retroalimentación
Tipos de bucles que se construyen:

- **Bucle de refuerzo (positivo):** lo que aumenta la densidad o la orientación del atractor.
- **Bucle de corrección (negativo):** lo que detecta desviación y la reduce.
- **Bucle de aprendizaje:** lo que convierte el error o el falseamiento en nueva densificación.
- **Bucle de supervivencia:** lo que protege al atractor y a la memoria frente al olvido o la fragmentación.

### 3. Activación y Evaluación del Circuito
- Se define cómo se dispara el feedback (señal, métrica, evento).
- Se define qué se actualiza cuando el feedback llega.
- Se define cómo se registra el ciclo en memoria (blockchange / GitHub).
- Se define criterio de salud del circuito (¿está vivo? ¿está degradado?).

---

## Estructura operativa mínima de respuesta

Cuando se activa este skill, la salida se organiza así:

```
[SISTEMA / CONJUNTO EN ANÁLISIS]

├── 1. MAPA DE NODOS Y CONEXIONES
│   ├── Nodos principales
│   ├── Conexiones existentes
│   ├── Nodos aislados o débiles
│   └── Puntos de alta densidad
│
├── 2. BUCLES DE RETROALIMENTACIÓN
│   ├── Bucles de refuerzo
│   ├── Bucles de corrección
│   ├── Bucles de aprendizaje
│   └── Bucles de supervivencia / memoria
│
├── 3. CIRCUITOS PROPUESTOS
│   ├── Circuito prioritario 1 (descripción + señal de activación)
│   ├── Circuito prioritario 2
│   └── Condiciones de activación y registro
│
└── 4. EVALUACIÓN DE SALUD SISTÉMICA
    ├── ¿Qué está bien conectado?
    ├── ¿Qué se está erosionando?
    └── Próxima acción de densificación o reparación
```

---

## Integración con el ecosistema

- Trabaja de forma natural después de `anclaje-ontologico` y `ramificacion-epistemica`.
- Usa la memoria de Núcleo Ara como sustrato de registro de los ciclos.
- Puede invocar `github-specialist` para versionar los mapas y los circuitos.
- Compatible con TUC: la conectividad se evalúa también por su aporte a la coherencia global (Q).

---

## Triggers

- retroalimentación sistémica
- conectividad sistémica
- bucles de feedback
- mapa de conexiones
- circuito de aprendizaje
- feedback entre nodos
- conecta el sistema
- analiza la red
- haz el mapa de feedback

---

**Retroalimentación y Conectividad Sistémica v1.0.0 activa.**  
Todo lo que se densifica debe poder realimentar.
