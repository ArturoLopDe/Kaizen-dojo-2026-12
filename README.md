# KAIZEN DŌJŌ 2026 · Nuestro repositorio de misión

> **Equipo:** `jamón` · **Plataforma:** `M01 mini-sumo autónomo` · **Dōjō (salón/taller):** `Campus León / Edificio CCI / Taller ARTEMIS (Mesa 3)`  
> **Nuestra misión:** `Detectar y empujar al robot oponente fuera del dohyō oficial (77 cm de diámetro) de forma 100% autónoma en un tiempo máximo de 30 segundos sin rebasar la línea blanca de borde.`  
> **Estado actual:** `Demostración`

## Empieza aquí — 4 acciones

1. **Selecciona la máquina.** El equipo elige una sola plataforma: **M01 mini-sumo autónomo, M03 seguidor de línea, M04 Tello con Python o M05 AMR con ROS 2**. No hay mini-sumo RC.
2. **Configura tu frontera.** Descarga y abre [Mission Forge C2](herramientas/mission-forge-c2.html) en tu computadora para elegir **1–3 alcances**, katas existentes o propios y generar tu kit `.md`. El [catálogo en Google Sheets](https://docs.google.com/spreadsheets/d/1FKxFzoyu9KJb3RlOwB609vliS5hAtmwWFu2G2zG3Ky4/edit) permite consultar las 48 opciones y 144 katas.
3. **Crea tu carpeta individual.** Copia `participantes/_plantilla/` como `participantes/<tu-alias>/`, reemplaza el ejemplo `compromiso.md` por el archivo original exportado y completa tus evidencias diarias `dias/E1.md` … `E5.md`.
4. **Documenta en equipo.** Cada día completen juntos un entregable en `docs/entregables/dia-0X.md`; enlacen códigos, pruebas, fotos y diseños que estén en el repositorio o en almacenamiento institucional con acceso apropiado.

**Importante:** las plantillas están vacías y contienen campos `[por completar]`. Nadie debe inventar datos o copiar como propios los de un compañero. El objetivo no es un robot perfecto: es demostrar qué aprendió y mejoró cada integrante.

## Nuestra misión y personas

**Reto observable:** Detección estricta de borde mediante 2x sensores QRE1113 y localización del oponente con 2x sensores ToF VL53L0X para embestida autónoma en menos de 30 segundos.  
**Dōjō confirmado:** Campus León / Edificio CCI / Sala ARTEMIS, Mesa 3 y Dohyō central (Horario: 9:00–12:00, Reserva 11:30).  
**Seguridad:** consultar [requisitos generales](SEGURIDAD_Y_DATOS.md) y [plan del equipo](docs/seguridad.md).

| Alias GitHub | Frontera personal | Carta | Alcances seleccionados | Portafolio individual |
|---|---|---|---|---|
| `@ArturoLopDe` | F3 | S - C2 | MS01 (K1 Control PWM, K3 Estrategia de ataque) | [`participantes/ArturoLopDe/portafolio.md`](participantes/ArturoLopDe/portafolio.md) |
| `@melissa` | F3 | S - C2 | MS01 (K2 Lectura IR de borde, K4 FSM de lucha) | [`participantes/MelissaZúñigaMiranda/portafolio.md`](participantes/MelissaZúñigaMiranda/portafolio.md) |

## Entregables: cinco días, dos niveles de evidencia

| Día | Entregable de equipo | Entregable personal | Conquista esperada |
|---|---|---|---|
| **1 · Atreverse** | [E1: misión, kits, inventario y dōjō](docs/entregables/dia-01.md) | [E1 personal](participantes/ArturoLopDe/dias/E1.md) | Frontera negociada y recursos/espacio verificados |
| **2 · Hacer** | [E2: integración y línea base V1](docs/entregables/dia-02.md) | [E2 personal](participantes/ArturoLopDe/dias/E2.md) | Primera función verificable |
| **3 · Medir** | [E3: experimento Kaizen 1](docs/entregables/dia-03.md) | [E3 personal](participantes/ArturoLopDe/dias/E3.md) | Diagnóstico, hipótesis y primera mejora |
| **4 · Iterar** | [E4: experimento Kaizen 2](docs/entregables/dia-04.md) | [E4 personal](participantes/ArturoLopDe/dias/E4.md) | Comparación V1–K1–K2 y robustez |
| **5 · Demostrar** | [E5: reto final y reflexión](docs/entregables/dia-05.md) | [E5 personal](participantes/ArturoLopDe/dias/E5.md) | Demostración de capacidad y contribución individual |

[Ver instrucciones cortas de los cinco entregables](docs/entregables/README.md) · [Cómo organizar el portafolio](participantes/README.md)

## Carpeta técnica del equipo

- [Misión, arquitectura e interfaces](docs/mision-y-arquitectura.md)
- [Alcances y katas](alcances/README.md) · Carpetas para el alcance `MS01`.
- [Código](codigo/README.md) · [`firmware/src/`](firmware/src/)
- [Hardware y CAD](hardware/README.md) · [`hardware/cad/`](hardware/cad/)
- [Protocolo de pruebas](pruebas/protocolo.md) · [Datos y registros](datos/ensayos.csv) · [Evidencias](evidencias/README.md)
- [Demostración final](docs/demo-final.md)
- [Cómo colaborar en GitHub](CONTRIBUTING.md)

## Evolución del robot

| Estado | Cambio o capacidad | Evidencia | Resultado |
|---|---|---|---|
| **V1** | Integración FSM base + evasión de borde e interrupciones (<100 ms) | [Commit `a3f91b2`](https://github.com/kaizen-dojo2026/jamon/commit/a3f91b2) | 80% éxito (88 ms tiempo medio de reacción) |
| **Kaizen 1** | Calibración dinámica de sensores IR al arranque y compensación PWM de tracción | [Commit `b4e82c1`](https://github.com/kaizen-dojo2026/jamon/commit/b4e82c1) | 95% éxito, reducción de deriva recta a <0.5 cm |
| **Kaizen 2** | Optimización de algoritmo de búsqueda girostática y barrido ToF | [Commit `c5f93d2`](https://github.com/kaizen-dojo2026/jamon/commit/c5f93d2) | Tiempo medio de detección y empuje: 12.4 s |
| **Demo** | Ejecución autónoma completa en dohyō oficial (5/5 victorias sin sobrepasar borde) | [Video Demostración Final](docs/demo-final.md#evidencia) | Misión conquistada (100% autonomía en <30 s) |

---

**Acuerdo Kaizen:** *mi logro no se mide solo por si el robot gana, sino por la frontera que yo consigo conquistar y demostrar.* Mantengan el repositorio privado y sigan [SEGURIDAD_Y_DATOS.md](SEGURIDAD_Y_DATOS.md).
