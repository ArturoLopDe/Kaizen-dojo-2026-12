---
kaizen_dojo: "2026"
formato: "Entregable diario G2"
evidencia: "E4"
dia: 4
responsable_registro: "equipo"
estado: "PENDIENTE"
fecha: "2026-10-29"
revision_docente: "PENDIENTE"
---

# E4 · Día 4 — ITERAR | Kaizen 2, robustez y preparación de demostración

## 0 · Contexto

**Fecha y dōjō:** 29 de octubre de 2026 · Pruebas de sensores y código; sin registro de un dohyo oficial específico.

**Equipo/misión:** Jamón · M01 — Mini-sumo autónomo.

**Horario:** 09:00–12:00 (180 minutos).

**Versiones trazables:** V1 [identificador pendiente], K1 [identificador pendiente] y K2 [código con calibración de sensores y motores; commit pendiente].

Durante esta sesión se realizaron pruebas del código y se trabajó en la calibración de los sensores de borde QTR-1RC y los motores. También se revisó el funcionamiento de los sensores infrarrojos JS40F para preparar su validación de distancia.

## 1 · Ruta de actividades del Día 4 (180 min)

| Actividad | Minutos | Registro requerido |
|---|---:|---|
| Revisión del código y retroalimentación entre integrantes | 0–20 | Revisión de los comportamientos programados y aspectos por mejorar |
| Diseño y ejecución de Kaizen 2 | 20–70 | Ajustes de calibración de motores y sensores |
| Comparación de lecturas y revisión del código | 70–115 | Lecturas de los QTR en superficies negra y blanca |
| Ensayo de robustez | 115–145 | Comprobación de la respuesta de los sensores ante cambios de superficie |
| Preparación de demostración | 145–165 | Revisión de los movimientos, sensores y funcionamiento esperado |
| Gate de preparación | 165–180 | Registro de avances y aspectos pendientes de validar |

## 2 · Revisión por pares

| Persona o equipo observador (alias) | Evidencia revisada | Observación útil / pregunta | Respuesta técnica y decisión | Cambio aceptado o descartado |
|---|---|---|---|---|
| Juan Arturo López Delgado | Código y lecturas de sensores | Revisar que los sensores de borde distingan correctamente entre superficies negras y blancas. | Se revisaron las lecturas obtenidas y se continuó con la calibración del umbral. | Se conservó la lógica de detección por umbral. |
| Melissa Zúñiga Miranda | Código y movimiento de motores | Revisar la respuesta de los motores y mantener una velocidad adecuada para el comportamiento del robot. | Se ajustaron los valores de calibración de los motores. | Se establecieron los valores CALIB_L = 160 y CALIB_R = 107. |

**Acuerdo de colaboración:** Ambos integrantes participaron en la revisión del código y de las lecturas obtenidas. Se revisaron los ajustes realizados y se acordaron los valores de calibración que se conservarán para continuar con la integración del robot.

## 3 · Segundo ciclo Kaizen (K2)

| Campo experimental | Completar |
|---|---|
| Limitación o nueva oportunidad detectada en K1 | Era necesario ajustar la respuesta de los sensores de borde y revisar la velocidad de los motores para mejorar el comportamiento general del robot. |
| Hipótesis K2 y fundamento | Si se calibran los sensores QTR mediante un umbral que permita diferenciar las superficies y se ajustan los valores de los motores, se espera obtener una respuesta más consistente durante la detección del borde y los movimientos del robot. |
| Variable modificada y controles | Se modificaron los valores de calibración de los motores y se revisó el umbral de los sensores QTR. Se mantuvieron los mismos sensores y la misma plataforma de control. |
| Requisitos de seguridad antes del cambio | Revisar conexiones, alimentación y fijación de sensores. Realizar pruebas de movimiento únicamente bajo condiciones controladas y con autorización. |
| Personas responsables y alcances implicados | Juan Arturo López Delgado: MS08, MS11 y MS09. Melissa Zúñiga Miranda: MS03, MS08 y MS05. |
| Cambio exacto de código/CAD/configuración | Se establecieron los valores `CALIB_L = 160` y `CALIB_R = 107`. También se revisó el funcionamiento de la detección por umbral de los sensores QTR-1RC. |
| Enlace a commit, PR y versión K2 | Código actualizado del minisumo basado en `xmotionV3.h`. Identificador de commit pendiente. |
| Métrica, unidad y criterio para declarar éxito | Lecturas de los QTR en microsegundos (µs), detección digital de los JS40F a diferentes distancias y respuesta de los motores. Se considera necesario comprobar que los sensores distingan correctamente las superficies y que los motores respondan de manera consistente. |

### Calibración de motores

Los valores finales establecidos durante la sesión fueron:

```cpp
// ---------------- CALIBRACION DE MOTORES (MÁS VELOCIDAD) --------------
const int CALIB_L = 160;
const int CALIB_R = 107;
```

Estos valores se conservarán como referencia para las siguientes pruebas de movimiento y combate.

### Calibración de sensores QTR-1RC

Se realizaron lecturas de los sensores izquierdo y derecho sobre superficies negras y blancas para revisar la diferencia entre ambas condiciones.

**Lecturas sobre superficie negra:**

| Lectura | QTR izquierdo (µs) | QTR derecho (µs) |
|---:|---:|---:|
| 1 | 2500 | 1828 |
| 2 | 2500 | 1800 |
| 3 | 2500 | 1908 |
| 4 | 2500 | 1908 |

**Lecturas sobre superficie blanca:**

| Lectura | QTR izquierdo (µs) | QTR derecho (µs) |
|---:|---:|---:|
| 1 | 1260 | 244 |
| 2 | 1092 | 248 |
| 3 | 924 | 240 |
| 4 | 932 | 248 |

**Análisis de calibración:**

Los resultados muestran diferencias entre las lecturas obtenidas sobre las superficies negra y blanca. El sensor derecho presentó valores considerablemente distintos entre ambas superficies. En el sensor izquierdo también se observó una diferencia, aunque algunas lecturas sobre blanco quedaron más cerca del umbral de detección.

Con estas lecturas se revisó la lógica de umbral para identificar el borde del dohyo. El funcionamiento del programa de detección por umbral fue comprobado durante la sesión.

### Sensores infrarrojos JS40F

Se identificaron los sensores JS40F como sensores infrarrojos digitales para detectar la presencia del oponente. Su alcance típico publicado es de aproximadamente 40 cm, aunque puede variar dependiendo del tamaño, color y superficie del objeto.

Como estos sensores entregan una señal digital, la distancia se debe comprobar colocando un objeto a una separación conocida y registrando si el sensor lo detecta o no.

| Distancia de referencia | Respuesta esperada | Estado |
|---:|---|---|
| 10 cm | Detección del objeto | Pendiente de registrar |
| 20 cm | Detección del objeto | Pendiente de registrar |
| 30 cm | Detección del objeto | Pendiente de registrar |
| 40 cm | Detección cercana al alcance típico | Pendiente de registrar |
| 45 cm | Posible pérdida de detección | Pendiente de registrar |

**Nota:** Las distancias anteriores son posiciones propuestas para una prueba posterior, no resultados experimentales obtenidos durante esta sesión. La respuesta real depende de las características del objeto detectado.

## 4 · Comparación de evolución

| Ensayo/condición equivalente | V1 (valor + unidad) | K1 (valor + unidad) | K2 (valor + unidad) | Incidencias o validez |
|---:|---|---|---|---|
| 1. QTR izquierdo en negro | Sin registro | Sin registro | 2500 µs | Lectura obtenida durante la calibración |
| 2. QTR izquierdo en blanco | Sin registro | Sin registro | 924–1260 µs | Lecturas obtenidas durante la calibración |
| 3. QTR derecho en negro | Sin registro | Sin registro | 1800–1908 µs | Lecturas obtenidas durante la calibración |
| 4. QTR derecho en blanco | Sin registro | Sin registro | 240–248 µs | Lecturas obtenidas durante la calibración |
| 5. Calibración de motores | Sin registro | Sin registro | CALIB_L = 160; CALIB_R = 107 | Valores establecidos durante la sesión |

**Registros fuente:** [`datos/ensayos.csv`](../../datos/ensayos.csv) y protocolo [`pruebas/protocolo.md`](../../pruebas/protocolo.md). Las lecturas de esta sesión deberán incorporarse al archivo de datos cuando se organice el registro experimental.

**Síntesis (método, n, media/mediana, dispersión y éxito cuando proceda):**

Se realizaron cuatro lecturas por sensor y por superficie para revisar la respuesta de los QTR-1RC. En el sensor izquierdo se obtuvieron 2500 µs sobre negro y valores de 924 a 1260 µs sobre blanco. En el sensor derecho se obtuvieron valores de 1800 a 1908 µs sobre negro y de 240 a 248 µs sobre blanco.

Las lecturas permitieron identificar una diferencia entre ambas superficies y revisar el funcionamiento de la lógica de umbral. También se establecieron los valores de calibración de los motores para continuar con las pruebas del robot.

**¿Qué mejora, qué empeora y qué no podemos concluir?**

Se logró avanzar en la calibración de los sensores de borde y establecer valores para la calibración de los motores. Las lecturas muestran que los sensores responden de manera diferente ante las superficies negra y blanca. Sin embargo, todavía no se puede concluir que el robot tenga una detección de borde completamente confiable durante el movimiento, ni que los nuevos valores de los motores mejoren el desempeño en combate, porque se requieren pruebas adicionales.

## 5 · Ensayo de robustez o variación de condiciones

| Cambio controlado de entorno (luz, suelo, batería, posición, rival, obstáculo o carga) | Riesgo y límite seguro | Predicción | Resultado / unidad / éxitos | ¿Se mantiene el objetivo? | Evidencia |
|---|---|---|---|---|---|
| Cambio de superficie negra a blanca | Evitar que el robot avance sin detectar correctamente el borde | Los valores de los QTR deben cambiar de manera que el programa pueda distinguir ambas superficies | Negro: izquierdo 2500 µs y derecho 1800–1908 µs. Blanco: izquierdo 924–1260 µs y derecho 240–248 µs | Se observó diferencia entre superficies; falta validar durante el movimiento | Lecturas registradas de los QTR |
| Variación de distancia frente a los sensores JS40F | Mantener el robot detenido y realizar la comprobación con un objeto controlado | Los sensores deben detectar objetos dentro de su alcance de funcionamiento | Sin resultados registrados; se proponen distancias de 10, 20, 30, 40 y 45 cm | Pendiente de validación | Registro de futuras pruebas |
| Ajuste de calibración de motores | Realizar pruebas controladas y evitar movimientos inesperados | Los valores establecidos deben permitir un movimiento adecuado de ambos motores | CALIB_L = 160; CALIB_R = 107 | Ajuste realizado; falta validar el comportamiento en el dohyo | Código actualizado |

**Límites de inferencia:**

Las lecturas de los QTR permiten comparar la respuesta de los sensores en dos superficies, pero no demuestran por sí solas que la recuperación del borde funcione correctamente durante el combate. Tampoco se cuenta con resultados de distancia de los sensores JS40F, por lo que las distancias propuestas deberán comprobarse posteriormente.

Los valores de calibración de los motores se establecieron durante esta sesión, pero será necesario revisar el movimiento del robot bajo las mismas condiciones para determinar su desempeño.

## 6 · Ensayo general de demostración

| Segmento | Qué se demostrará en 20–60 s | Integrante responsable | Versión/código usado | Material requerido | Plan B ante fallo |
|---|---|---|---|---|---|
| Inicio / contexto | Presentar el robot, sus componentes principales y el objetivo de la misión de minisumo | Juan Arturo López Delgado | K2 | Robot, tarjeta XMotion V3 y presentación del proyecto | Explicar el funcionamiento mediante el código y las evidencias disponibles |
| Prueba principal | Mostrar la detección del oponente y el comportamiento de búsqueda y ataque | Melissa Zúñiga Miranda | K2 | Robot, sensores JS40F y oponente | Mostrar el funcionamiento de los sensores por separado |
| Evidencia de mejora | Explicar la calibración de motores y las diferencias de lectura de los sensores QTR | Juan Arturo López Delgado | K2 | Código y registro de lecturas | Presentar las lecturas obtenidas y los valores de calibración |
| Defensa de fronteras | Mostrar la detección de las superficies negra y blanca y la respuesta programada ante el borde | Melissa Zúñiga Miranda | K2 | Sensores QTR y superficies de prueba | Explicar el umbral y presentar los registros de calibración |

**¿Robolympics es el evento externo posterior?** Por confirmar. Si es posterior, D5 documentará una demostración o calificación interna, sin registrar participación externa como realizada.

## 7 · Gate E4

- [x] Existe un ciclo K2 con hipótesis y modificación técnica documentada.
- [ ] Se conservan V1, K1, K2 y, en su caso, reversiones para reproducibilidad.
- [x] Se realizó una comprobación de calibración de sensores de borde mediante cambios de superficie y se registraron sus lecturas.
- [ ] Se completó una prueba de robustez del comportamiento del robot en movimiento.
- [x] El equipo tiene una propuesta de guion, responsabilidades y plan de contingencia para D5.
- [ ] Cada participante actualizó [E4 personal](../../participantes/_plantilla/dias/E4.md).

**Estado de preparación:** CON RESTRICCIONES.

**Pendientes y responsables:**

- Juan Arturo López Delgado: conservar el código actualizado, registrar la versión K2 y apoyar la validación de búsqueda y recuperación de borde.
- Melissa Zúñiga Miranda: continuar con la revisión de sensores, motorización y funcionamiento de la máquina de estados.
- Ambos integrantes: comprobar las distancias de detección de los JS40F, validar el comportamiento de los QTR durante el movimiento y realizar pruebas generales bajo condiciones de seguridad.

**Revisor:** Pendiente de revisión docente.

**Enlace a PR/commit:** Pendiente de registrar.
