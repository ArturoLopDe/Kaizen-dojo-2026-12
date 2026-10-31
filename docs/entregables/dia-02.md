---
kaizen_dojo: "2026"
formato: "Entregable diario G2"
evidencia: "E2"
dia: 2
responsable_registro: "jamón"
estado: Melissa Zúñiga
fecha: "2026-10-27"
revision_docente: "PENDIENTE"
---

# E2 · Día 2 — HACER | Primera integración funcional y línea base V1

> **Regla:** sustituir los corchetes, registrar lo realmente observado y enlazar a evidencias del repositorio. **No inventar datos ni marcar pruebas no realizadas.** Los archivos del equipo resumen el trabajo compartido; las reflexiones y evidencias personales van en `participantes/<alias>/dias/E2.md`.

## 0 · Identificación y continuidad

| Campo | Dato |
|---|---|
| Fecha, equipo, misión y plataforma | 2026-10-27; Equipo jamón; M01 mini-sumo autónomo |
| Dōjō real y mesa/zona utilizada | Campus León / Edificio CCI / Taller ARTEMIS — Mesa 3 y Dohyō oficial de pruebas |
| Estado del gate E1 / cambios desde D1 | APROBADO CON CONDICIONES (Condición: Aislamiento térmico/eléctrico en LiPo completado a las 8:45 AM por @melissa) |
| Kit por integrante / compromisos modificados | [`participantes/ArturoLopDe/compromiso.md`](https://github.com/ArturoLopDe/Kaizen-dojo-2026-12/blob/877291e4d2149f269798aebd85ed7786a9f97909/participantes/ArturoLopDe/compromiso-kaizen-juan-arturo-lopez-delgado.md) y [`participantes/MelissaZúñigaMiranda/compromiso.md`](https://github.com/ArturoLopDe/Kaizen-dojo-2026-12/blob/925e8c4a48ada76b545811e7d561c545f6164929/participantes/MelissaZ%C3%BA%C3%B1igaMiranda/compromiso.md) |
| Materiales recibidos y pendientes | Recibidos: MAT-001 a MAT-005. Pendientes: Disipador térmico secundario para driver (Responsable: @ArturoLopDe) |
| Objetivo técnico del Día 2 | Lograr la integración V1 (FSM de evasión de borde + detección de rival) y registrar la línea base de respuesta en dohyō |

## 1 · Ruta de las actividades de hoy (180 min)

| Bloque | Minutos | Registro requerido / evidencia |
|---|---:|---|
| Revisión de misión y compromisos | 0–15 | Verificación de aislamiento en batería LiPo; desbloqueo del Gate E1 |
| Microlección aplicada | 15–35 | Ajuste de Máquina de Estados Finitos (FSM) no bloqueante con millis() y lecturas analógicas |
| Katas de integración | 35–105 | @melissa: Kata 2 (Lectura IR e interrupciones) / @ArturoLopDe: Kata 1 (Control PWM y puentes H) |
| Ensayos iniciales / línea base | 105–145 | Protocolo de 5 corridas de detección de borde y empuje en dohyō de 77 cm |
| Consolidación de evidencia | 145–170 | Registro de datos en `datos/ensayos.csv` y subida de logs a `participantes/` |
| Gate E2 | 170–180 | Evaluación del estado V1 y definición de prioridades Kaizen 1 |

## 2 · Microlección e integración por alcances

**Tema que resolvió un problema real del equipo:** Implementación de FSM sin retardos bloqueantes (`delay()`) para garantizar tiempo de respuesta <50 ms ante la línea blanca. **Material / referencia utilizada:** Apuntes de arquitectura de control en tiempo real y FSM del dōjō.

| Alias | Alcance | Kata seleccionado / nuevo | Acción técnica ejecutada | Archivo, commit o plano | Estado (pendiente/probado/bloqueado) | Dependencia de otro integrante |
|---|---|---|---|---|---|---|
| @ArturoLopDe | MS01 | K1 (Control PWM) | Mapeo de curvas PWM y puente H TB6612FNG con reversa rápida | [`firmware/src/motors.cpp`](../../firmware/src/motors.cpp) | Probado | Módulo FSM de @melissa |
| @melissa | MS01 | K2 (Lectura IR de borde) | Interrupción analógica / muestreo a 100 Hz de sensores QRE1113 | [`firmware/src/sensors_ir.cpp`](../../firmware/src/sensors_ir.cpp) | Probado | Ninguna |

## 3 · Estado de integración V1

| Subsistema | Entrada | Salida esperada | Responsable | Prueba de integración y observación | Evidencia |
|---|---|---|---|---|---|
| Estructura/mecánica | Ensamble 10x10 cm y cuña | Inclinación <15° y agarre | @ArturoLopDe | Ajuste de cuña contra superficie plana; no atasca el avance | [participantes/ArturoLopDe/dias/E2.md#mecanica] |
| Energía y accionamiento | Batería LiPo 7.4V a TB6612FNG | PWM a motores N20 | @melissa | Avance constante a 80% PWM sin caídas de voltaje en lógica | [participantes/MelissaZúñigaMiranda/dias/E2.md#power] |
| Sensores/percepción | Sensores QRE1113 y ToF VL53L0X | Voltajes 0.4V-4.1V y distancia en mm | @melissa | Discriminación correcta de borde blanco y objeto rival a 25 cm | [participantes/MelissaZúñigaMiranda/dias/E2.md#sensores] |
| Control/software | Eventos de sensores en FSM | Cambio de estado BÚSQUEDA -> ATAQUE -> EVASIÓN | @ArturoLopDe | Transición inmediata a EVASIÓN al tocar línea blanca | [participantes/ArturoLopDe/dias/E2.md#fsm] |
| Integración global | Sistema autónomo en dohyō | Ciclo completo de búsqueda, ataque y retroceso en borde | Ambos | Bucle continuo verificado en 5 ensayos | [participantes/ArturoLopDe/dias/E2.md#video-v1] |

**Versión identificable:** Commit `a3f91b2` / Firmware `v1.0.0-alpha`. **Comportamiento que SÍ demuestra V1:** El robot detecta el borde blanco del dohyō y retrocede inmediatamente; detecta rival a menos de 25 cm y conmuta a embestida a 100% PWM. **Lo que aún falla:** Desviación de 3 cm hacia la derecha en desplazamientos rectos mayores a 1.5 metros.

## 4 · Protocolo y línea base del robot (datos observados)

Completar también [`pruebas/protocolo.md`](../../pruebas/protocolo.md) y registrar datos crudos en [`datos/ensayos.csv`](../../datos/ensayos.csv).

| Campo de validez experimental | Respuesta obligatoria |
|---|---|
| Pregunta y resultado que se quiere medir | Tiempo de reacción desde la detección de línea blanca hasta la detención/reversa completa del robot |
| Métrica primaria + unidad (segundos, %, cm, rad, etc.) | Tiempo de respuesta en milisegundos (ms) |
| Éxito/fallo (criterio cuantitativo u observable) | Éxito: Reacción en <100 ms sin que la cuña o ruedas rebasen el borde blanco exterior |
| Lugar, configuración, pista/dohyō/estaciones/marcadores | Dohyō oficial de 77 cm en Sala ARTEMIS, luz ambiental controlada de taller |
| Configuración del robot: batería, firmware y sensores | LiPo 7.4V (100% carga: 8.4V), Firmware v1.0.0-alpha, 2x QRE1113, 2x VL53L0X |
| Condiciones controladas: luz, rival, posición de inicio, etc. | Posición inicial a 15 cm del borde apuntando hacia afuera a 45°; rival estático en centro |
| Número de corridas planeadas / ejecutadas | 5 planeadas / 5 ejecutadas |
| Procedimiento reproducible, responsable y seguridad/aborto | Encendido autónomo tras 5s de retardo oficial. Responsable: @ArturoLopDe. Aborto: Interruptor maestro LiPo |
| Datos sin procesar y video/foto corta | Registro en `datos/ensayos.csv` y evidencias en repositorios personales |

| Ensayo | Condición inicial | Valor (+ unidad) | Éxito/fallo | Observación relevante / incidencia |
|---:|---|---|---|---|
| 1 | Batería 8.4V, inicio cuadrante N | 78 ms | Éxito | Detención limpia y viraje de 90° hacia el interior |
| 2 | Batería 8.3V, inicio cuadrante E | 82 ms | Éxito | Retroceso correcto; ligero derrape de rueda derecha |
| 3 | Batería 8.2V, inicio cuadrante S | 115 ms | Fallo parcial | Rebasó el borde por 2 mm antes de invertir giro por sombra de usuario |
| 4 | Batería 8.1V, inicio cuadrante O | 80 ms | Éxito | Respuesta inmediata sin desplazamiento indeseado |
| 5 | Batería 8.0V, inicio cuadrante N | 85 ms | Éxito | Comportamiento consistente de FSM |

**Línea base resumida (no fabricada):** Total de ensayos: 5. Media de tiempo de respuesta: 88 ms (Mediana: 82 ms). Tasa de éxito: 80% (4/5). Caso descartado/fallido en Ensayo 3 atribuido a variación momentánea de luz ambiental sobre el sensor QRE1113 (se ajustará el umbral en Kaizen 1).

## 5 · Decisiones al cierre, bloqueos y Kaizen de mañana

| Fallo o cuello de botella observado | Hipótesis preliminar | Prioridad | Responsable | Material / apoyo necesario |
|---|---|---|---|---|
| Desviación en trayectoria recta hacia la derecha | Fricción desigual en reductora o descalibración leve de PWM en canal B | Media | @ArturoLopDe | Multímetro / Tacómetro de banco |
| Sensibilidad a sombras externas en sensor IR | Umbral estático rígido en software | Alta | @melissa | Calibración dinámica al encendido |

- [x] Hay prototipo V1, subsistema funcional verificable o fallo reproducible con condiciones registradas.
- [x] Existen archivos fuente o evidencia técnica enlazada, además de videos de uso controlado cuando correspondan.
- [x] Hay protocolo reproducible y valores basales con unidad o justificación de lo que no pudo medirse.
- [x] Cada alumno actualizó su [E2 personal](../../participantes/_plantilla/dias/E2.md) con contribución propia y límite de capacidad actual.
- [x] Se mantuvieron límites de seguridad y protección de datos.

**Gate E2:** APROBADO. **Revisor:** @ProfCDuqueTec / Camilo René Duque Becerra **Fecha:** 2026-10-27.

**Próxima prioridad de Kaizen 1:** Implementar rutina de calibración dinámica de sensores IR al arranque y compensación de PWM para corrección de deriva recta. **Enlace al commit/PR:** [Pull Request #2 - Integración V1 / jamón](https://github.com/kaizen-dojo2026/jamon/pull/2)
