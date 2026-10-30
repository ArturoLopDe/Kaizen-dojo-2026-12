---
kaizen_dojo: 2026
formato: Entregable diario G2
evidencia: E2
dia: 2
responsable_registro: equipo
estado: PENDIENTE
fecha: 2026-10-28
revision_docente: PENDIENTE
---

# E2 · Día 2 — HACER | Primera integración funcional y línea base V1

## 1. Identificación y continuidad

| Campo | Información |
|---|---|
| Equipo | Jamón |
| Misión | M01 — Mini-sumo autónomo |
| Día de trabajo | 2 |
| Fecha | 28 de octubre de 2026 |
| Horario | 09:00–12:00 |
| Duración | 3 horas |
| Integrantes | Juan Arturo López Delgado y Melissa Zúñiga Miranda |
| Plataforma de control | XMotion All In One Controller V3 |
| Motores | JSumo Core 6 V / 750 RPM |
| Sensores de oponente | 4 sensores digitales JS40F |
| Sensores de borde | 2 sensores QTR-1RC |
| Alimentación | Batería LiPo 3S de 11.4 V y 300 mAh |
| Estado del trabajo | Investigación y modificaciones al código |

### Continuidad con E1

Durante el primer día de trabajo, realizado el 27 de octubre, se establecieron los objetivos generales del proyecto y se revisaron los componentes que conforman el robot minisumo.

Para el segundo día se decidió enfocar el trabajo en investigar estrategias utilizadas en competencias de minisumo y revisar la lógica de programación del robot. A partir de la información consultada, se realizaron modificaciones al código con la intención de mejorar el comportamiento del robot durante la búsqueda y el enfrentamiento contra el oponente.

En esta sesión no se realizaron pruebas físicas, por lo que todavía no se cuenta con resultados experimentales que permitan confirmar el funcionamiento de las modificaciones.

### Alcance individual

| Integrante | Microalcances relacionados |
|---|---|
| Juan Arturo López Delgado | MS08 — FSM de combate; MS11 — Recuperación de borde; MS09 — Estrategia de búsqueda |
| Melissa Zúñiga Miranda | MS03 — Motorización; MS08 — FSM; MS05 — Sensores de borde |

Los dos integrantes participaron en la revisión de estrategias y en el análisis de posibles mejoras para el comportamiento general del robot.

---

## 2. Ruta de actividades — 180 minutos

| Horario | Duración | Actividad | Resultado de la actividad |
|---|---:|---|---|
| 09:00–09:20 | 20 min | Revisión del estado del proyecto y del código disponible | Identificación de las partes del programa que podían mejorarse |
| 09:20–10:10 | 50 min | Investigación de estrategias utilizadas en competencias de minisumo | Recopilación de ideas relacionadas con búsqueda, ataque y defensa |
| 10:10–10:40 | 30 min | Análisis de las estrategias investigadas y su posible aplicación | Selección de comportamientos que podían incorporarse al programa |
| 10:40–11:30 | 50 min | Modificación de la lógica de programación | Ajustes en las rutinas de búsqueda y comportamiento de combate |
| 11:30–11:50 | 20 min | Revisión del código modificado | Identificación de aspectos que deberán comprobarse posteriormente |
| 11:50–12:00 | 10 min | Registro de avances y pendientes | Organización de las siguientes actividades |

**Tiempo total:** 180 minutos (3 horas).

---

## 3. Microlección e integración por alcance

### Investigación de estrategias de minisumo

La mayor parte de la sesión se dedicó a investigar las estrategias que utilizan otros robots minisumo durante las competencias. Se revisaron diferentes formas de localizar al oponente, aproximarse a él y realizar ataques.

Entre los comportamientos estudiados se encuentran:

- **Búsqueda por barrido:** el robot gira para ampliar el área que puede detectar mientras busca al oponente.
- **Búsqueda mediante giros:** utiliza movimientos de rotación para localizar al contrincante cuando no se encuentra dentro del rango de los sensores.
- **Ataque directo:** cuando se detecta al oponente, el robot avanza para intentar empujarlo fuera del dohyo.
- **Ataque con ajuste de dirección:** modifica su trayectoria dependiendo del lado en el que se detecta al oponente.
- **Comportamiento defensivo:** mantiene una estrategia de búsqueda y respuesta para evitar movimientos innecesarios.
- **Recuperación del borde:** busca alejarse de la línea de peligro cuando los sensores detectan el límite del dohyo.

La investigación permitió comprender que el comportamiento del robot no debe limitarse a avanzar constantemente, sino que necesita combinar la detección, la búsqueda y la toma de decisiones.

### Integración de las estrategias en el código

Después de revisar las estrategias, se trabajó directamente sobre el código del minisumo utilizando la biblioteca `xmotionV3.h`.

Se revisaron principalmente las funciones relacionadas con la búsqueda del oponente, la defensa y la respuesta ante la detección de los sensores.

| Integrante | Alcance | Trabajo realizado durante la sesión |
|---|---|---|
| Juan Arturo López Delgado | MS08 — FSM de combate | Revisión de los estados y comportamientos que intervienen durante el enfrentamiento |
| Juan Arturo López Delgado | MS11 — Recuperación de borde | Revisión de la lógica encargada de responder cuando se detecta el límite del dohyo |
| Juan Arturo López Delgado | MS09 — Estrategia de búsqueda | Investigación de movimientos de búsqueda y ajustes en la lógica correspondiente |
| Melissa Zúñiga Miranda | MS03 — Motorización | Revisión de los movimientos y velocidades utilizados por el programa |
| Melissa Zúñiga Miranda | MS08 — FSM | Análisis de la relación entre la detección del oponente y las decisiones del robot |
| Melissa Zúñiga Miranda | MS05 — Sensores de borde | Revisión de la lógica de lectura y respuesta de los sensores QTR-1RC |

**Resultado de la integración:** se realizaron modificaciones al código con base en la investigación. Sin embargo, todavía no se puede confirmar que los cambios produzcan una mejora en el desempeño del robot, debido a que no se realizaron pruebas físicas.

---

## 4. Estado de integración V1

### Estado general

| Elemento | Estado | Observaciones |
|---|---|---|
| Plataforma XMotion V3 | Identificada | Se trabaja con la tarjeta de control del robot |
| Motores | Identificados | JSumo Core de 6 V y 750 RPM |
| Sensores de oponente | Identificados | Cuatro sensores digitales JS40F |
| Sensores de borde | Identificados | Dos sensores QTR-1RC |
| Lógica de búsqueda | Modificada | Se realizaron ajustes después de investigar distintas estrategias |
| Lógica de ataque | Revisada | Se analizó el comportamiento esperado al detectar al oponente |
| Lógica de defensa | Revisada | Se revisaron los movimientos de búsqueda y respuesta |
| Recuperación de borde | Pendiente de validación | No se realizaron pruebas físicas |
| Integración completa | Pendiente | Se requiere comprobar el comportamiento con el hardware |
| Funcionamiento autónomo | Pendiente de validación | No se cuenta todavía con resultados experimentales |

### Descripción de la versión V1

La versión V1 corresponde al código que se modificó durante esta sesión después de investigar diferentes estrategias de minisumo.

El objetivo de esta versión es contar con una lógica de comportamiento que permita al robot buscar al oponente, ajustar su dirección cuando lo detecte y responder ante situaciones relacionadas con el borde del dohyo.

Esta versión todavía debe considerarse experimental, ya que las modificaciones únicamente se revisaron desde el código y no se comprobaron mediante pruebas físicas.

---

## 5. Protocolo de pruebas y línea base

### Objetivo

Establecer un procedimiento para comprobar posteriormente las modificaciones realizadas al código y evaluar el comportamiento del robot durante la búsqueda, detección del oponente, ataque y recuperación del borde.

### Condición de la sesión

Durante el segundo día no se realizaron pruebas físicas. El trabajo se concentró en la investigación y modificación del programa.

Por esta razón, no se registran mediciones de tiempo, distancias, porcentajes de detección ni resultados de enfrentamientos.

### Protocolo propuesto para la siguiente sesión

| Prueba | Procedimiento | Resultado esperado | Estado |
|---|---|---|---|
| P01 — Encendido | Verificar el encendido del sistema y la respuesta de la tarjeta | El sistema inicia correctamente | PENDIENTE |
| P02 — Sensores de oponente | Comprobar individualmente los cuatro sensores JS40F | Identificación correcta del oponente | PENDIENTE |
| P03 — Sensores de borde | Comprobar los dos sensores QTR-1RC | Detección del límite del dohyo | PENDIENTE |
| P04 — Búsqueda | Ejecutar la rutina de búsqueda sin un oponente presente | El robot realiza el movimiento programado | PENDIENTE |
| P05 — Ataque | Colocar un oponente dentro del rango de detección | El robot orienta su movimiento hacia el oponente | PENDIENTE |
| P06 — Recuperación | Simular la detección del borde bajo condiciones controladas | El robot se aleja del límite | PENDIENTE |
| P07 — Combate completo | Evaluar el comportamiento general en el dohyo autorizado | El robot ejecuta la secuencia de combate | PENDIENTE |

**Línea base experimental:** todavía no establecida.

Los resultados de estas pruebas deberán registrarse cuando se realicen. No se asignan valores iniciales porque durante esta sesión no se obtuvieron mediciones.

---

## 6. Decisiones, bloqueos y siguiente Kaizen

### Decisiones tomadas

1. Investigar estrategias utilizadas en competencias de minisumo antes de continuar modificando el comportamiento del robot.
2. Tomar como referencia diferentes métodos de búsqueda y ataque para mejorar la lógica del programa.
3. Continuar trabajando sobre la plataforma XMotion All In One Controller V3 y la biblioteca `xmotionV3.h`.
4. Mantener pendientes las pruebas físicas hasta contar con las condiciones de seguridad y autorización correspondientes.
5. Concentrar las fotografías y videos de las sesiones en una carpeta compartida de evidencias.

### Bloqueos y aspectos pendientes

| Bloqueo o pendiente | Impacto | Acción siguiente |
|---|---|---|
| Código todavía sin validar físicamente | No se puede confirmar el funcionamiento de las modificaciones | Realizar pruebas controladas |
| Sensores sin validación durante esta sesión | No se conoce su respuesta real dentro del programa modificado | Revisar lecturas individuales |
| Estrategias investigadas sin comprobar | No se puede determinar cuál ofrece mejores resultados | Comparar su funcionamiento en el dohyo |
| Línea base experimental inexistente | No es posible medir mejoras de desempeño | Registrar resultados de las primeras pruebas |
| Autorización y condiciones de seguridad para pruebas | Limita la validación física | Confirmar las condiciones antes de realizar pruebas dinámicas |

### Siguiente Kaizen

Para la siguiente sesión se propone continuar con la revisión del código y preparar la integración con el hardware.

Las actividades principales serán:

- Revisar que el código modificado compile correctamente.
- Comprobar las lecturas de los sensores de oponente y de borde.
- Verificar los movimientos de los motores.
- Realizar pruebas controladas de búsqueda y ataque cuando se cuente con autorización.
- Evaluar la recuperación del borde.
- Registrar los resultados para establecer una primera línea base experimental.

---

## 7. Gate E2 — Evaluación del segundo día

| Criterio | Estado | Comentario |
|---|---|---|
| Investigación de estrategias | COMPLETADO | Se revisaron diferentes comportamientos utilizados en minisumo |
| Revisión del programa | COMPLETADO | Se analizaron las funciones principales del código |
| Modificaciones al código | COMPLETADO | Se realizaron ajustes basados en la investigación |
| Integración con hardware | PENDIENTE | No se realizó una validación física |
| Pruebas de sensores | PENDIENTE | No se realizaron pruebas durante esta sesión |
| Pruebas de movimiento | PENDIENTE | No se realizaron pruebas durante esta sesión |
| Línea base experimental | PENDIENTE | No existen mediciones registradas |
| Evidencias | EN RECOPILACIÓN | Fotografías y videos concentrados en una carpeta compartida |
| Revisión docente | PENDIENTE | Sujeta a validación |

### Resultado del Gate E2

El segundo día permitió avanzar en la parte de investigación y programación del proyecto. Se revisaron estrategias utilizadas en competencias de minisumo y se realizaron modificaciones al código para mejorar la lógica de búsqueda y combate del robot.

Aunque se obtuvo un avance en el desarrollo del programa, todavía es necesario comprobar su funcionamiento mediante pruebas físicas. Por lo tanto, el equipo considera que el entregable E2 documenta un avance de programación e investigación, pero no representa todavía una integración validada ni una línea base experimental.

**Estado final del E2: PENDIENTE DE VALIDACIÓN.**
