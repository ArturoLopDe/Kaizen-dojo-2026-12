# KAIZEN DŌJŌ 2026 · Nuestro repositorio de misión

> **Equipo:** `Jamón` · **Plataforma:** `M01 Mini-sumo autónomo` · **Dōjō (salón/taller):** `Por confirmar`
>
> **Nuestra misión:** `Construir y programar un minisumo autónomo capaz de detectar oponentes, buscar, atacar y evitar salir del dohyo, para completar combates y conseguir la victoria.`
>
> **Estado actual:** `Demostración realizada / K2`

## Empieza aquí — 4 acciones

1. **Selecciona la máquina.** El equipo eligió la plataforma **M01 mini-sumo autónomo**. El robot utiliza una tarjeta XMotion V3 y funciona de manera autónoma durante los combates.
2. **Configura tu frontera.** Se trabajaron los alcances de programación, control de combate, motorización, búsqueda y detección de borde. Las actividades se enfocaron en integrar los componentes y mejorar el funcionamiento del robot.
3. **Crea tu carpeta individual.** Cada integrante debe contar con su carpeta personal para registrar sus alcances, actividades y evidencias diarias. Los portafolios individuales permiten identificar las aportaciones de cada integrante.
4. **Documenta en equipo.** Cada día se elaboró un entregable compartido en `docs/entregables/dia-0X.md`, además de conservar fotografías, videos, código y registros de pruebas en la carpeta compartida del equipo.

**Importante:** cada integrante debe documentar sus propias aportaciones y utilizar evidencias que correspondan a su trabajo. El objetivo no es solamente conseguir que el robot gane, sino demostrar los aprendizajes y las mejoras realizadas durante el proyecto.

## Nuestra misión y personas

**Reto observable:** Construir un minisumo autónomo que detecte al oponente mediante sensores infrarrojos JS40F, lo busque y ataque, mientras utiliza sensores QTR-1RC para reconocer los límites del dohyo y evitar salir de la superficie. El criterio de éxito de la demostración fue completar el combate y conseguir la victoria.

**Dōjō confirmado:** Espacio de trabajo y demostración del Kaizen Dōjō. Edificio, salón y horario exactos por confirmar.

**Seguridad:** consultar [requisitos generales](SEGURIDAD_Y_DATOS.md) y [plan del equipo](docs/seguridad.md).

| Alias GitHub | Frontera personal | Carta | Alcances seleccionados | Portafolio individual |
|---|---|---|---|---|
| `Juan Arturo López Delgado` | Programación y estrategia de combate | Por confirmar | `MS08, MS11, MS09` | `participantes/juan/portafolio.md` |
| `Melissa Zúñiga Miranda` | Motorización y sensores de borde | Por confirmar | `MS03, MS08, MS05` | `participantes/melissa/portafolio.md` |

## Entregables: cinco días, dos niveles de evidencia

| Día | Entregable de equipo | Entregable personal | Conquista esperada |
|---|---|---|---|
| **1 · Atreverse** | [E1: misión, kits, inventario y dōjō](docs/entregables/dia-01.md) | [E1 personal](participantes/_plantilla/dias/E1.md) | Definición de la misión, organización de alcances y revisión de recursos. |
| **2 · Hacer** | [E2: integración y línea base V1](docs/entregables/dia-02.md) | [E2 personal](participantes/_plantilla/dias/E2.md) | Desarrollo inicial e integración de los componentes. |
| **3 · Medir** | [E3: experimento Kaizen 1](docs/entregables/dia-03.md) | [E3 personal](participantes/_plantilla/dias/E3.md) | Investigación de estrategias y modificaciones al código. |
| **4 · Iterar** | [E4: experimento Kaizen 2](docs/entregables/dia-04.md) | [E4 personal](participantes/_plantilla/dias/E4.md) | Calibración de sensores QTR-1RC, ajuste de motores y mejora de detección por umbral. |
| **5 · Demostrar** | [E5: reto final y reflexión](docs/entregables/dia-05.md) | [E5 personal](participantes/_plantilla/dias/E5.md) | Mejora de estrategia defensiva, calibración para otro dohyo, implementación del arrancador y victoria en la demostración. |

[Ver instrucciones cortas de los cinco entregables](docs/entregables/README.md) · [Cómo organizar el portafolio](participantes/README.md)

## Carpeta técnica del equipo

- [Misión, arquitectura e interfaces](docs/mision-y-arquitectura.md)
- [Alcances y katas](alcances/README.md) · Se documentan los alcances seleccionados por los integrantes.
- [Código](codigo/README.md) · [Hardware y CAD](hardware/README.md)
- [Protocolo de pruebas](pruebas/protocolo.md) · [Datos y registros](datos/README.md) · [Evidencias](evidencias/README.md)
- [Demostración final](docs/demo-final.md)
- [Cómo colaborar en GitHub](CONTRIBUTING.md)

## Evolución del robot

| Estado | Cambio o capacidad | Evidencia | Resultado |
|---|---|---|---|
| **V1** | Primera versión del código y configuración inicial del minisumo. | Código y registros iniciales del equipo. | Se estableció la lógica básica de funcionamiento. |
| **Kaizen 1** | Investigación de estrategias de minisumo y modificaciones al código de búsqueda y combate. | Código actualizado y registro de actividades del Día 3. | Se avanzó en la organización de la estrategia del robot. |
| **Kaizen 2** | Calibración de sensores QTR-1RC, ajuste de umbrales y calibración de motores. | Mediciones de sensores y código actualizado del Día 4. | Funcionó la detección por umbral y se ajustaron los motores. |
| **Demo** | Mejora de estrategia defensiva, recalibración para otro dohyo e implementación del arrancador en OTR (A1). | Mediciones finales, fotografías y video de demostración. | El robot funcionó correctamente y ganó el combate. |

---

**Acuerdo Kaizen:** *Mi logro no se mide solo por si el robot gana, sino por la frontera que yo consigo conquistar y demostrar.*

Mantengan el repositorio privado y sigan [SEGURIDAD_Y_DATOS.md](SEGURIDAD_Y_DATOS.md).
