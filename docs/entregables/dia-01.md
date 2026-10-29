---
kaizen_dojo: "2026"
formato: "Entregable diario G2"
evidencia: "E1"
dia: 1
responsable_registro: "jamón"
estado: "PENDIENTE"
fecha: "2026-10-26"
revision_docente: "PENDIENTE"
---

# E1 · Día 1 — ATREVERSE | Contrato de misión, inventario y dōjō

> **Regla:** sustituir los corchetes, registrar lo realmente observado y enlazar a evidencias del repositorio. **No inventar datos ni marcar pruebas no realizadas.** Los archivos del equipo resumen el trabajo compartido; las reflexiones y evidencias personales van en `participantes/<alias>/dias/E1.md`.

## 0 · Identificación, equipo y logística del dōjō

| Campo obligatorio | Dato |
|---|---|
| Fecha y horario de esta sesión | 2026-10-26; 9:00–12:00, 180 min |
| Nombre / alias del equipo | jamón |
| Misión / plataforma | M01 mini-sumo autónomo |
| Objetivo verificable del robot (una frase) | Detectar y empujar al robot oponente fuera del dohyō oficial (77 cm de diámetro) de forma 100% autónoma en un tiempo máximo de 30 segundos sin rebasar la línea blanca de borde. |
| **Dōjō asignado — campus, edificio y sala/taller exactos** | **Campus León / Edificio CCI / Sala o taller ARTEMIS** |
| Puesto o zona dentro del dōjō | Mesa 3 y Dohyō oficial de pruebas M01 |
| Horario / reserva confirmada | 26 de octubre, 2026; 11:30 |
| Responsable del espacio y contacto institucional | Héctor Javier Arismendi Valle, hector.arismendi@tec.mx |
| Acceso, aforo y ajustes de accesibilidad | Horario de 6:00-10:00, 28 personas, dojo minisumo, extensiones, mesas, sillas |
| Salidas, botiquín, extintor y punto de reunión | Extintor junto a puerta principal CCI, Botiquín en entrada Artemis, Punto de reunión: Explanada CCI |
| Zonas segregadas por riesgo | Área de soldadura y corte en perímetro de Artemis |
| Ubicación de materiales y resguardo nocturno | Taller Artemis, MakerSpace; Melissa Zúñiga Miranda |
| Plan de sustitución si falla el espacio | Taller CTA |
| Instructor o supervisor presente en la sesión | @ProfCDuqueTec / Camilo René Duque Becerra |

> ⛔ **No se permite avanzar a pruebas físicas sin dōjō concreto y autorización del responsable.** No inventar salón, número de laboratorio ni recursos que no hayan sido confirmados.

## 1 · Integrantes, responsabilidades, accesibilidad y decisiones (0–15 min)

| Alias GitHub | Rol inicial | Carta y frontera (D/S/E; F1–F4) | Alcances ID (1–3) | Kit personal (archivo) | Necesidad de apoyo o accesibilidad acordada |
|---|---|---|---|---|---|
| @ArturoLopDe | Pruebas y documentación | S - F3 - C2 | MS01 | [`participantes/ArturoLopDe/compromiso.md`](https://github.com/ArturoLopDe/Kaizen-dojo-2026-12/blob/877291e4d2149f269798aebd85ed7786a9f97909/participantes/ArturoLopDe/compromiso-kaizen-juan-arturo-lopez-delgado.md) | Ninguna requerida; horarios flexibles acordados |
| @melissa | Integración y pruebas | S - F3 - C2 | MS01 | [`participantes/MelissaZúñigaMiranda/compromiso.md`](https://github.com/ArturoLopDe/Kaizen-dojo-2026-12/blob/925e8c4a48ada76b545811e7d561c545f6164929/participantes/MelissaZ%C3%BA%C3%B1igaMiranda/compromiso.md) | Apoyo en manejo de cargas prolongadas si aplica |

**Acuerdo de colaboración:** Las decisiones técnicas se toman por consenso tras pruebas en banco. En desacuerdos, el supervisor (@ProfCDuqueTec) actúa como mediador. Se rota el uso del área de soldadura y se programan pausas de 5 min cada 50 min.

## 2 · Demostración de la plataforma y seguridad (15–35 min)

| Elemento | Observación directa | Evidencia / vínculo |
|---|---|---|
| Plataforma base inspeccionada (estado, modelo, ID inventario) | Chasis Mini-Sumo V1 completo, cableado ordenado, ID: MS-2026-01 | [participantes/MelissaZúñigaMiranda/dias/E1.md#fotos-chasis] |
| Funciones existentes y límites comprobados | Motores con reductora funcionales; lectura de sensores de borde operativa | [participantes/ArturoLopDe/dias/E1.md#video-motores] |
| Paro de emergencia / desconexión segura ensayados | Interruptor maestro de corte de alimentación de batería LiPo probado exitosamente | [docs/seguridad.md#paro-emergencia] |
| Restricciones de competición o exhibición verificadas | Dimensiones dentro de 10x10 cm y peso menor a 500 g verificados | [docs/reglamento_minisumo.pdf] |
| Riesgos vistos y medidas activas | Bordes filosos en cuña de aluminio y riesgo de corto en LiPo mitigados con aislamiento | [docs/seguridad.md#riesgos-m01] |

**Normas específicas según misión:**
- **M01:** protecciones de alimentación; desarmar motores antes de tocar ruedas; dohyō delimitado, rival de referencia y bordes seguros.
- **M03:** pista despejada, altura/posición de sensores controlada, baterías y ruedas comprobadas.
- **M04:** espacio interior autorizado, observador humano, altura y desplazamientos limitados, baterías y aterrizaje inmediato; *verificar modelo real de Tello*.
- **M05:** ROS 2 y TF/navegación listos; límites de velocidad, sensor de obstáculos, paro seguro y zona de tránsito marcada.

## 3 · Diagnóstico práctico colectivo (35–65 min)

**Condición inicial V0 de la plataforma:** Kit de chasis ensamblado con motores y controlador base; pendiente calibrar sensores IR de borde y pulir cuña metálica.

| Prueba diagnóstica | Condición y procedimiento | Resultado observado / unidad | Problema / causa probable | Evidencia |
|---|---|---|---|---|
| 1: movimiento o comunicación | Avance recto a 100% PWM durante 2 segundos en superficie plana | Desviación hacia la derecha de 3.5 cm | Fricción desigual en rueda izquierda o ligera diferencia en reductores | [participantes/ArturoLopDe/dias/E1.md#log-mov] |
| 2: lectura de sensor | Detección de contraste negro/blanco con sensor QRE1113 a 3 mm del dohyō | Variación de voltaje de 0.4 V a 4.1 V | Correcto; requiere calibración de umbral en firmware | [participantes/MelissaZúñigaMiranda/dias/E1.md#sensores] |
| 3: comportamiento de la misión | Búsqueda girostática de rival falso en el centro del dohyō | Giro continuo sin detenerse al cruzar blanco | Umbral de sensibilidad en sensor ToF muy elevado | [participantes/ArturoLopDe/dias/E1.md#prueba-mision] |

**Capacidades ya disponibles y dependencias:** Módulo de control de motores PWM reutilizable. La rutina de evasión depende de la calibración de interrupciones de lectura analógica a cargo de @melissa.

## 4 · Integración de Mission Forge C2 y pacto de alcances (65–100 min)

Cada participante debe colocar el archivo **Markdown original generado por la web** en:

`participantes/<alias>/compromiso.md`

Se conserva íntegro (incluido el frontmatter y la lista de katas). Los nuevos alcances/katas diseñados por el participante quedan claramente marcados como *propuesta propia* y requieren aprobación técnica.

**Catálogo de referencia:** [Google Sheets C2](https://docs.google.com/spreadsheets/d/1FKxFzoyu9KJb3RlOwB609vliS5hAtmwWFu2G2zG3Ky4/edit) · **Configurador Mission Forge:** [`herramientas/mission-forge-c2.html`](../../herramientas/mission-forge-c2.html) (descárgalo y ábrelo en el navegador; funciona sin Internet).

| Alias | Kit enlazado | Alcance principal | Complementos | Katas elegidos o nuevos | Horas mín.–máx. | Evidencia final esperada | Negociación aprobada |
|---|---|---|---|---|---|---|---|
| @ArturoLopDe | [`participantes/ArturoLopDe/compromiso.md`](https://github.com/ArturoLopDe/Kaizen-dojo-2026-12/blob/877291e4d2149f269798aebd85ed7786a9f97909/participantes/ArturoLopDe/compromiso-kaizen-juan-arturo-lopez-delgado.md) | MS01 | Ninguno | K1 (Control PWM), K3 (Estrategia de ataque) | 6–8 h | CAD ensamblado + prueba de empuje | Sí (@ProfCDuqueTec) |
| @melissa | [`participantes/MelissaZúñigaMiranda/compromiso.md`](https://github.com/ArturoLopDe/Kaizen-dojo-2026-12/blob/925e8c4a48ada76b545811e7d561c545f6164929/participantes/MelissaZ%C3%BA%C3%B1igaMiranda/compromiso.md) | MS01 | Ninguno | K2 (Lectura IR de borde), K4 (FSM de lucha) | 6–8 h | Firmware integrado + log de bordes | Sí (@ProfCDuqueTec) |

**Resultado de negociación grupal:** Se estableció una Máquina de Estados Finitos (FSM). Prioridad 1: Detección estricta de línea blanca para evitar caídas; Prioridad 2: Detección y embestida del oponente.

## 5 · Inventario exhaustivo y especificación de materiales (obligatorio)

### 5.1 Inventario maestro del equipo

Completar **cada recurso requerido**: estructura, electrónica, actuadores, sensores, herramientas, consumibles, instrumentos, software, datos, red, espacios de ensayo y elementos de seguridad. Añadir filas sin límite.

| ID | Categoría | Material o recurso (especificación exacta: modelo, medida, versión o característica) | Cantidad requerida + unidad | Cantidad confirmada | Fuente/proveedor o dueño | Ubicación física o ruta digital | Responsable | Estado (disponible/reservado/falta) | Alternativa compatible | Día requerido |
|---|---|---|---|---|---|---|---|---|---|---|
| MAT-001 | Robot/plataforma | Chasis aleación aluminio Mini-Sumo 10x10 cm | 1 ud. | 1 ud. | Laboratorio CCI | Taller Artemis / Estación 3 | @melissa | Disponible | Impresión 3D PLA | D1 |
| MAT-002 | Actuadores | Motorreductor N20 12V 600 RPM | 2 ud. | 2 ud. | Kit del laboratorio | Taller Artemis / Caja M01 | @ArturoLopDe | Disponible | Motor N20 1000 RPM | D1 |
| MAT-003 | Electrónica | Driver de motor Dual H-Bridge TB6612FNG | 1 ud. | 1 ud. | Almacén Artemis | Taller Artemis / Caja M01 | @melissa | Disponible | L298N Mini | D1 |
| MAT-004 | Sensores | Sensor de distancia ToF VL53L0X | 2 ud. | 2 ud. | Kit personal | Taller Artemis / Caja M01 | @ArturoLopDe | Disponible | Ultrasónico HC-SR04 | D1 |
| MAT-005 | Zona de pruebas | Dohyō oficial de pruebas (77 cm diámetro, borde blanco) | 1 ud. | 1 ud. | Taller Artemis | Sala ARTEMIS - Zona central | @melissa | Reservado | Pista de vinil | D1 |

También disponible el archivo [`datos/inventario_materiales.csv`](../../datos/inventario_materiales.csv) para registrar muchos materiales sin agrandar esta tabla.

### 5.2 Lista de cotejo específica por plataforma (elegir solo la misión asignada)

| Misión | Revisar y especificar (marca/modelo/cantidad reales) |
|---|---|
| M01 · Mini-sumo autónomo | Chasis de aluminio de 10x10 cm con cuña frontal; ruedas de silicón con 2x motores N20; driver TB6612FNG y controlador ESP32/Arduino; batería LiPo 2S 7.4V 450mAh con fusible de 5A; 2x sensores QRE1113 y 2x ToF VL53L0X; dohyō oficial de 77 cm. |

**Enlaces a fichas técnicas / instrucciones de conexión, fabricación y seguridad:** [docs/seguridad.md](../../docs/seguridad.md) · [docs/hardware/tb6612fng_pinout.pdf](docs/hardware/tb6612fng_pinout.pdf)

### 5.3 Riesgos de recursos y abastecimiento

| Bloqueante | A qué alcance afecta | Solución prevista / fecha y responsable | Impacto si no se resuelve |
|---|---|---|---|
| Pérdida de tracción por desgaste en llantas de silicón | Embestida (MS01) | Limpieza con alcohol isopropílico antes de pruebas / 2026-10-27 @ArturoLopDe | Pérdida de empuje ante rival |

**Materiales completos para ejecutar el Día 2:** Sí. **Confirmado por:** @ProfCDuqueTec y @melissa a las 2026-10-26 11:45.

## 6 · Kata 0 — exploración técnica de arranque (100–160 min)

| Integrante/alcance | Pregunta técnica | Mini-prueba o prototipo de exploración | Resultado o error observado | Evidencia enlazada | Acción necesaria antes de D2 |
|---|---|---|---|---|---|
| @ArturoLopDe / MS01 | ¿El driver responde a inversión rápida sin sobrecalentarse? | Inversión de giro de motores PWM cada 500 ms por 3 min | Temp. dentro de rango normal (<40°C), respuesta directa | [participantes/ArturoLopDe/dias/E1.md#kata0] | Colocar disipador térmico por prevención |
| @melissa / MS01 | ¿El ToF detecta un objetivo mate a 30 cm? | Barrido con objetivo de prueba a distintas distancias | Lectura precisa hasta 28 cm; cae a partir de 30 cm | [participantes/MelissaZúñigaMiranda/dias/E1.md#kata0] | Ajustar umbral límite de ataque a 25 cm en código |

**Integración entre subequipos:** Se validó la alimentación compartida a 5V para sensores y el pulso de paro por software (<100 ms).

## 7 · Cierre: contrato técnico y puerta de salida E1 (160–180 min)

- [x] El objetivo colectivo tiene condición de éxito verificable.
- [x] Cada estudiante depositó **su kit Markdown original** en `participantes/<alias>/compromiso.md`.
- [x] Cada estudiante completó [E1 personal](../../participantes/_plantilla/dias/E1.md) y definió frontera, evidencia y alcance negociado.
- [x] El inventario está **completo** y cada recurso indica cantidad, especificación, disponibilidad y responsable.
- [x] Se asignó **dōjō específico** con edificio, salón/taller, horarios, supervisión y autorización.
- [x] Se inspeccionaron riesgos, paro y condiciones de seguridad de la plataforma.
- [x] Se identificaron dependencias y bloqueos del Día 2; están bajo control o se ajustó la misión.
- [x] El profesor aprobó el alcance y la seguridad, o registró observaciones y una alternativa viable.

**Estado del gate:** APROBADO CON CONDICIONES.

**Condiciones, responsables, fecha y próxima decisión:** Asegurar aislamiento eléctrico/térmico en la batería LiPo previo a pruebas dinámicas a velocidad máxima en D2. Responsable: @melissa. Fecha límite: 2026-10-27 09:00.

**Revisor docente:** @ProfCDuqueTec / Camilo René Duque Becerra · **Enlace a commit/PR:** [Pull Request #1 - Integración E1 / jamón](https://github.com/kaizen-dojo2026/jamon/pull/1)

**Criterio mínimo E1:** existe un contrato de misión y frontera individual, hay evidencia del punto de partida, un inventario verificable y un espacio de trabajo autorizado. La ausencia de algún material crítico NO debe esconderse.
