---
kaizen_dojo: "2026"
formato: "Entregable diario G2"
evidencia: "E3"
dia: 3
responsable_registro: "equipo"
estado: "PENDIENTE"
fecha: "2026-10-28"
revision_docente: "PENDIENTE"
---

# E3 · Día 3 — MEDIR Y APRENDER | Kaizen 1: ensayo, hipótesis y mejora

> **Nota:** Durante esta sesión el trabajo se concentró en investigación y modificaciones al código. No se realizaron pruebas físicas, por lo que los resultados experimentales y la comparación V1 contra K1 permanecen pendientes.

## 0 · Contexto de investigación de hoy

**Fecha/equipo/misión:** 28 de octubre de 2026 · Jamón · M01 — Mini-sumo autónomo.

**Dōjō exacto:** No se realizaron actividades físicas dentro del dohyo durante esta sesión.

**Versión de partida:** Código de control del minisumo basado en la biblioteca `xmotionV3.h`. Identificador de commit o etiqueta V1 pendiente de registrar.

**Protocolo E2:** Pendiente de completar y vincular el archivo correspondiente. Durante esta sesión no se ejecutaron pruebas físicas.

## 1 · Ruta del Día 3 (180 min)

**Horario de trabajo:** 09:00–12:00.

| Actividad | Minutos | Evidencia a registrar |
|---|---:|---|
| Revisar el código y reconocer oportunidades de mejora | 0–15 | Código inicial y funciones que se analizaron |
| Investigación de estrategias de minisumo | 15–40 | Información consultada sobre búsqueda, ataque y defensa |
| Diagnóstico del programa | 40–80 | Revisión de las funciones de búsqueda, combate y recuperación de borde |
| Kaizen 1: modificación del código | 80–125 | Cambios realizados en la lógica del programa |
| Revisión del código modificado | 125–160 | Revisión de las modificaciones y posibles comportamientos esperados |
| Documentar y reflexionar | 160–180 | Registro de avances, pendientes y siguientes actividades |

**Duración total:** 180 minutos (3 horas).

## 2 · Problema, hipótesis y trazabilidad

| Campo | Completar |
|---|---|
| Fallo / oportunidad de mejora observada (con evidencia) | Se identificó la oportunidad de mejorar la estrategia de búsqueda y el comportamiento del robot durante un enfrentamiento. El programa necesitaba una lógica que permitiera buscar al oponente y orientar el movimiento de acuerdo con su detección. |
| Dónde se presenta y cuántas veces | En la lógica de búsqueda y combate del programa. No se registró un número de fallos porque no se realizaron pruebas físicas. |
| Diagnóstico: causas alternativas que se consideraron | Se consideró que la estrategia de búsqueda podía mejorarse mediante diferentes patrones de giro y movimiento. También se revisó la relación entre la detección de los sensores y las decisiones de movimiento del robot. |
| Hipótesis contrastable: si cambio X, espero que Y ocurra porque Z | Si se modifica la lógica de búsqueda y orientación del robot, se espera que pueda localizar al oponente de manera más eficiente, porque contará con movimientos de búsqueda y respuestas mejor organizadas según la detección de sus sensores. |
| Variable independiente que se modifica | Lógica de búsqueda y comportamiento de combate del programa. |
| Métrica de resultado con unidad y criterio de mejora | Tiempo de detección del oponente en segundos y porcentaje de detecciones correctas. Estas métricas quedan pendientes de medición. |
| Variables que se mantendrán iguales | Hardware, sensores, motores, alimentación, configuración del robot y condiciones del dohyo durante futuras pruebas comparativas. |
| Ensayos requeridos y forma de muestreo | Se proponen cinco ensayos por versión, V1 y K1, bajo condiciones equivalentes. Todavía no se han realizado. |
| Riesgo de sesgo/confusión y cómo se mitigará | Las diferencias en la posición del oponente, distancia inicial, orientación y condiciones de la superficie pueden afectar los resultados. Se deberán mantener las mismas condiciones en cada comparación. |
| Parada de seguridad / condición de aborto | Detener inmediatamente el robot si se detecta un comportamiento inesperado, riesgo de salida del dohyo, calentamiento anormal o cualquier condición insegura. Las pruebas dinámicas requieren autorización y condiciones de seguridad adecuadas. |

## 3 · Colaboración y cambio técnico Kaizen 1

| Alias y alcance | Kata asociado (código o propio) | Qué cambió exactamente | Por qué | Código/CAD/commit y responsable de revisión | Validación de interfaz |
|---|---|---|---|---|---|
| Juan Arturo López Delgado — MS08, MS11 y MS09 | Búsqueda, FSM de combate y recuperación de borde | Se revisó y modificó la lógica relacionada con la búsqueda del oponente y los comportamientos de combate y recuperación. | Incorporar estrategias investigadas y mejorar la organización de las respuestas del robot. | Código del minisumo basado en `xmotionV3.h`. Commit pendiente de identificar. | Pendiente de pruebas físicas. |
| Melissa Zúñiga Miranda — MS03, MS08 y MS05 | Motorización, FSM y sensores de borde | Participó en la revisión de los movimientos, la lógica de combate y la relación entre sensores y decisiones del programa. | Revisar que las estrategias propuestas consideren tanto el movimiento como la detección del oponente y del borde. | Código del minisumo basado en `xmotionV3.h`. Commit pendiente de identificar. | Pendiente de pruebas físicas. |

**Identificador de versión K1:** Código modificado durante la sesión del 28 de octubre. El identificador de commit o etiqueta queda pendiente.

**Otras modificaciones involuntarias o perturbaciones:** No se registraron modificaciones involuntarias. No se realizaron pruebas físicas ni cambios mecánicos durante esta sesión.

## 4 · Ensayos comparables

**Enlace a datos crudos CSV:** [`../../datos/ensayos.csv`](../../datos/ensayos.csv) (pendiente de generar cuando se realicen las pruebas).

**Protocolo:** [`../../pruebas/protocolo.md`](../../pruebas/protocolo.md) (pendiente de completar y validar).

| Prueba emparejada o bloque | Condición/escenario idéntico | V1, valor + unidad | K1, valor + unidad | Cambio / resultado | Incidencia o desviación |
|---:|---|---|---|---|---|
| 1 | Búsqueda del oponente | Sin medición | Sin medición | Pendiente | No se realizó |
| 2 | Detección frontal del oponente | Sin medición | Sin medición | Pendiente | No se realizó |
| 3 | Detección lateral del oponente | Sin medición | Sin medición | Pendiente | No se realizó |
| 4 | Respuesta de ataque | Sin medición | Sin medición | Pendiente | No se realizó |
| 5 | Recuperación ante detección de borde | Sin medición | Sin medición | Pendiente | No se realizó |

**N válido V1 / K1:** 0 / 0.

**Resumen, variabilidad y tasa de éxito:** No existen resultados experimentales para calcular variabilidad, diferencias de desempeño o tasa de éxito. La sesión se enfocó en investigación y modificaciones al código.

**Incertidumbres/limitaciones:** No se comprobó físicamente el comportamiento de la nueva lógica. Tampoco se cuenta con mediciones de tiempo de detección, precisión de sensores o desempeño de ataque. Por lo tanto, todavía no es posible determinar si K1 representa una mejora frente a V1.

## 5 · Interpretación y decisión

- **¿La evidencia respalda, contradice o no permite decidir la hipótesis?** No permite decidir todavía. La investigación y las modificaciones realizadas justifican la propuesta de mejora, pero es necesario realizar pruebas físicas para comprobar si el comportamiento del robot realmente mejora.

- **Si no hubo mejora, qué aprendimos:** Todavía no se puede determinar si hubo una mejora. Sin embargo, la investigación permitió conocer diferentes estrategias de búsqueda y combate que pueden utilizarse para desarrollar un comportamiento más organizado en el robot.

- **¿Qué riesgo o compromiso generó el cambio?** Las modificaciones pueden generar comportamientos diferentes a los esperados cuando se ejecuten en el hardware real. También será necesario revisar que los movimientos de búsqueda y ataque no interfieran con la recuperación del borde.

- **Decisión:** Conservar K1 de manera provisional para realizar pruebas posteriores. No se considera una versión validada hasta comprobar su funcionamiento y compararlo con V1.

- **Siguiente pregunta para Kaizen 2:** ¿La nueva estrategia de búsqueda permite detectar y orientar al robot hacia el oponente con mayor rapidez y consistencia que la versión anterior?

## 6 · Puerta de salida E3

- [ ] V1 y K1 tienen identificadores o referencias inequívocas.
- [x] La hipótesis está conectada con una medida y un problema diagnosticado.
- [x] Se documentó una modificación técnica y sus responsables.
- [ ] Ensayos y resultados mantienen condiciones comparables o exponen diferencias explícitamente.
- [x] La conclusión es honesta, incluso si el resultado es negativo.
- [ ] Cada estudiante registró su [E3 personal](../../participantes/_plantilla/dias/E3.md).

**Gate E3:** CONDICIONADO.

**Revisor:** Pendiente de revisión docente.

**Enlace a PR/commit:** Pendiente de registrar.
