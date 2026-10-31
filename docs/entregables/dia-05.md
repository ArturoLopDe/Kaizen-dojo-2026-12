---
kaizen_dojo: "2026"
formato: "Entregable diario G2"
evidencia: "E5"
dia: 5
responsable_registro: "equipo"
estado: "PENDIENTE"
fecha: "2026-10-30"
revision_docente: "PENDIENTE"
---

# E5 · Día 5 — DEMOSTRAR | Desafío, defensa técnica y cierre Kaizen

## 0 · Identificación del evento y sus límites

| Campo | Valor |
|---|---|
| Fecha / equipo / misión y plataforma | 30 de octubre de 2026 / Jamón / M01 Mini-sumo autónomo / XMotion V3 |
| Dōjō o espacio exacto, bloque horario y supervisor | Espacio de demostración del Kaizen Dōjō / horario de la sesión / supervisor por confirmar |
| Modalidad real | Desafío y demostración interna |
| ¿Participación en Robolympics posterior? | No confirmada |
| Versión final congelada y enlace al código/CAD | Versión final K2 ajustada durante la sesión / enlace al repositorio pendiente |
| Objetivo demostrable y criterio de éxito | Demostrar el funcionamiento del minisumo, su estrategia defensiva, detección de borde y sistema de arranque. El criterio de éxito fue completar el combate y obtener la victoria. |
| Acceso autorizado a espectadores/evidencias | Evidencias concentradas en la carpeta compartida del equipo. Permisos específicos por confirmar. |

Durante el quinto día terminamos de ajustar el código del minisumo y mejoramos la estrategia defensiva. También realizamos una nueva calibración de los sensores QTR-1RC debido a que el dohyo utilizado era diferente al de las sesiones anteriores.

Otro cambio importante fue la implementación del arrancador. Como el puerto donde inicialmente se había conectado no funcionaba correctamente, decidimos utilizar la salida OTR (A1). Para poder instalarlo correctamente, realizamos la conexión mediante soldadura.

Finalmente, realizamos la demostración del robot, durante la cual todos los sistemas funcionaron correctamente y conseguimos ganar el combate.

## 1 · Ruta de la experiencia final (180 min)

| Actividad | Minutos | Evidencia requerida |
|---|---:|---|
| Revisión de seguridad y chequeo previo | 0–20 | Revisión de conexiones, sensores, batería y componentes. |
| Ajustes finales del código | 20–45 | Código actualizado con mejoras en la estrategia defensiva. |
| Calibración de sensores QTR-1RC | 45–75 | Mediciones sobre el nuevo dohyo. |
| Implementación del arrancador | 75–100 | Conexión en OTR (A1) y soldadura del cableado. |
| Preparación y demostración | 100–160 | Video y fotografías de la demostración. |
| Reflexión y cierre | 160–180 | Revisión de resultados y registro de mejoras. |
| **Total** | **180 min** | |

## 2 · Checklist de seguridad antes de operar

- [x] Revisión general de las conexiones eléctricas.
- [x] Revisión de los sensores QTR-1RC.
- [x] Revisión de la conexión del arrancador.
- [x] Comprobación del funcionamiento del código antes de la demostración.
- [x] Revisión de la batería y fijaciones del robot.
- [ ] Registro documental de autorización del supervisor y permisos de captura de imagen.

**Observación o NO-GO de seguridad:** Se detectó que el puerto utilizado inicialmente para el arrancador no funcionaba correctamente. Se cambió la conexión a OTR (A1) y se realizó la soldadura correspondiente para asegurar su instalación. Después del cambio se comprobó su funcionamiento.

**Autoriza:** Supervisor del evento por confirmar.

## 3 · Registro de demostración de la misión

Durante la demostración final, el minisumo funcionó correctamente y logró ganar el combate. Antes de participar se terminaron los ajustes del código, se mejoró la estrategia defensiva y se calibraron nuevamente los sensores de borde para adaptarlos al dohyo utilizado.

| Intento | Versión/condiciones | Métrica y unidad | Resultado/éxito-fallo | Incidente o razón de fallo | Evidencia |
|---:|---|---|---|---|---|
| 1 | Versión final / nuevo dohyo | Resultado del combate | Victoria | Sin fallas reportadas durante la demostración | Video y fotografías en carpeta compartida |

**Procedimiento y datos crudos:** Mediciones de los sensores QTR-1RC registradas durante la calibración y video de la demostración en la carpeta compartida del equipo.

**Resumen de resultados:** Se realizó una demostración y se obtuvo una victoria. Los sistemas de detección de borde y arranque funcionaron correctamente durante la actividad.

**Limitación:** No se registraron tiempos de combate, distancias de detección del oponente ni una serie de múltiples enfrentamientos, por lo que no se pueden calcular porcentajes de victoria o estadísticas de desempeño.

**Métrica M01:** Funcionamiento de la detección de borde, respuesta de la estrategia defensiva y resultado del combate. El robot consiguió completar la demostración y ganar.

### 3.1 Mediciones finales de sensores QTR-1RC

Debido a que se utilizó otro dohyo, fue necesario realizar una nueva calibración. Se registraron las siguientes lecturas:

| Prueba | QTR izquierdo (µs) | QTR derecho (µs) |
|---:|---:|---:|
| 1 | 2500 | 2500 |
| 2 | 2500 | 2500 |
| 3 | 2500 | 2500 |
| 4 | 2500 | 2500 |
| 5 | 2500 | 2264 |
| 6 | 176 | 108 |
| 7 | 176 | 108 |
| 8 | 176 | 108 |
| 9 | 176 | 108 |
| 10 | 172 | 116 |
| 11 | 176 | 108 |

**Promedios registrados:**

| Condición de lectura | QTR izquierdo (µs) | QTR derecho (µs) |
|---|---:|---:|
| Lecturas altas (primeras 5 pruebas) | 2500 | 2453 |
| Lecturas bajas (últimas 6 pruebas) | 175 | 109 |

Las lecturas muestran una diferencia clara entre los dos grupos de valores. Esto permitió ajustar nuevamente la detección por umbral para las condiciones del nuevo dohyo.

## 4 · Defensa individual de fronteras

| Alias | Alcance(s) original(es) | Qué aportó realmente / enlace a evidencia | Antes no podía... | Ahora puedo... | Demostración de capacidad ante otro | Feedback de par o profesor |
|---|---|---|---|---|---|---|
| Juan Arturo López Delgado | MS08 FSM combate, MS11 recuperación de borde y MS09 estrategia de búsqueda | Modificación del código, mejora de estrategia defensiva, calibración de sensores e implementación del arrancador. Evidencias en carpeta compartida. | Integrar todos los ajustes y comprobar su funcionamiento en el nuevo dohyo. | Ajustar la estrategia de combate, calibrar los sensores QTR-1RC e implementar el arrancador en otra salida. | Demostración del minisumo, que logró ganar el combate. | Se observó el funcionamiento correcto del robot durante la demostración. |
| Melissa Zúñiga Miranda | MS03 motorización, MS08 FSM y MS05 sensores de borde | Participación en los ajustes y pruebas finales del robot. Evidencias en carpeta compartida. | Validar el comportamiento final del robot con las condiciones del nuevo dohyo. | Participar en la calibración y comprobación del sistema integrado antes de la demostración. | Demostración final del robot durante el combate. | Se observó el funcionamiento correcto del robot durante la demostración. |

**Ver portafolios individuales:** `participantes/ArturoLopDe/compromiso-kaizen-juan-arturo-lopez-delgado.md` y `participantes/MelissaZúñigaMiranda/compromiso.md`.

## 5 · Evaluación de la experiencia y cierre Design Thinking

| Pregunta para validar la experiencia | Respuesta basada en evidencia |
|---|---|
| ¿Qué elecciones del catálogo C2 tuvieron sentido para diferentes niveles de entrada? | La integración progresiva de sensores, motores y lógica de control permitió trabajar por partes y después comprobar el funcionamiento del robot completo. |
| ¿Qué katas fueron útiles, redundantes o faltaron? | Las actividades de programación, calibración de sensores y pruebas de integración fueron las más útiles. Habría sido conveniente dedicar más tiempo a practicar con diferentes condiciones de dohyo. |
| ¿Los materiales y el dōjō habilitaron el trabajo sin exclusiones? | Se contó con los componentes necesarios para realizar los ajustes y la demostración. Fue necesario adaptar la conexión del arrancador para resolver el problema del puerto original. |
| ¿Hubo evidencia de dos ciclos de mejora técnica? | Sí. Primero se trabajó en la lógica de búsqueda, combate y detección de borde. Después se realizaron nuevos ajustes de estrategia defensiva, calibración para otro dohyo e implementación del arrancador. |
| ¿Qué se debería rediseñar para la próxima iteración? | Se debería preparar una conexión más accesible para el arrancador, documentar las conexiones eléctricas y realizar calibraciones previas para diferentes superficies. |
| ¿La experiencia protegió confianza, autonomía, pertenencia y seguridad? | El equipo pudo identificar problemas, proponer soluciones y realizar ajustes por cuenta propia. También se revisaron las conexiones y el funcionamiento antes de la demostración. |

**Feedback externo o de otra pareja/equipo:** No se cuenta con un registro específico de comentarios externos. El resultado observado durante la demostración fue positivo, ya que el robot funcionó correctamente y ganó el combate.

## 6 · Cierre, transferencia y archivo

- **Estado técnico final:** Funcional durante la demostración. El robot consiguió completar el combate y ganar, con funcionamiento correcto de los sensores de borde y del arrancador.
- **Logros colectivos y límites reales:** Se terminó de ajustar el código, se mejoró la estrategia defensiva, se calibraron los sensores QTR-1RC para el nuevo dohyo y se implementó el arrancador en OTR (A1). Como limitación, todavía sería conveniente realizar más combates para evaluar la consistencia del desempeño.
- **Qué reutilizaría una generación futura:** La lógica de detección por umbral, los valores de calibración de los sensores, la estrategia defensiva y la solución de conexión del arrancador en otra salida.
- **Qué falta antes de competencia externa (si la hubiera):** Realizar más pruebas en diferentes condiciones de dohyo, verificar nuevamente las conexiones, comprobar la autonomía de la batería y validar la estrategia contra diferentes oponentes.
- **Inventario devuelto/resguardado, responsable y lugar exacto:** Componentes del minisumo resguardados por el equipo. Responsable y ubicación exacta por registrar.
- **Archivo de evidencias, permisos de acceso y retención:** Fotografías y videos de las actividades concentrados en la carpeta compartida del equipo. Los permisos y el periodo de retención deben confirmarse.
- **Próximo experimento o kata que se exploraría:** Probar diferentes estrategias defensivas y de búsqueda contra distintos oponentes, además de medir el tiempo de respuesta de los sensores de borde.

### Gate E5

- [x] Demostración registrada mediante evidencias del equipo, con resultado de victoria.
- [ ] V1, K1, K2 y Vn tienen enlaces y registros coherentes.
- [ ] Cada estudiante completó [E5 personal](../../participantes/_plantilla/dias/E5.md) y defendió su frontera.
- [x] Se registraron observaciones para la fase de validación posterior del Design Thinking.
- [ ] Se documentaron formalmente la devolución de materiales y los permisos de acceso a evidencias.

**Revisión final docente:** PENDIENTE.  
**Fecha:** Por revisar.  
**Firma/alias:** Por revisar.
