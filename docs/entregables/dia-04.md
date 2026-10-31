# E4 — Día 4: Calibración, pruebas de sensores y preparación de demostración

## 0. Contexto de la sesión

| Dato | Descripción |
|---|---|
| Equipo | Jamón |
| Misión | M01 — Mini-sumo autónomo |
| Fecha | Jueves 29 de octubre de 2026 |
| Horario | 09:00–12:00 |
| Duración | 180 minutos |
| Integrantes | Juan Arturo López Delgado y Melissa Zúñiga Miranda |
| Objetivo | Probar el código, calibrar los sensores de borde y ajustar la velocidad de los motores. |

Durante esta sesión nos enfocamos en comprobar el funcionamiento del código del minisumo y realizar ajustes para mejorar su comportamiento. Principalmente trabajamos con los sensores QTR-1RC, revisando sus lecturas sobre superficies blancas y negras. También ajustamos la calibración de los motores para conseguir un movimiento más equilibrado.

## 1. Distribución de actividades (180 minutos)

| Actividad | Tiempo | Descripción |
|---|---:|---|
| Revisión del código | 25 min | Revisamos la lógica de detección de borde y el funcionamiento general. |
| Pruebas de sensores QTR-1RC | 45 min | Tomamos lecturas sobre superficies blancas y negras. |
| Ajuste de umbrales | 30 min | Modificamos y verificamos la detección mediante umbrales. |
| Calibración de motores | 30 min | Ajustamos los valores de velocidad de cada motor. |
| Pruebas de funcionamiento | 35 min | Comprobamos las respuestas del código después de los ajustes. |
| Registro de resultados | 15 min | Organizamos las mediciones y documentamos los cambios. |
| **Total** | **180 min** | |

## 2. Revisión entre integrantes

Se revisó el funcionamiento del código y la respuesta de los sensores para identificar posibles problemas antes de continuar con las pruebas del robot.

Los principales puntos revisados fueron:

- Que los sensores QTR-1RC distinguieran correctamente entre superficies blancas y negras.
- Que el código utilizara un umbral adecuado para detectar el borde.
- Que ambos motores tuvieran una calibración que permitiera un desplazamiento más equilibrado.
- Que los cambios realizados no afectaran la lógica general de búsqueda y combate.

Como resultado de la revisión, se identificó que era necesario ajustar los valores de calibración de los motores y verificar las lecturas de los sensores antes de continuar con las pruebas de movimiento.

## 3. Kaizen 2 — Segundo ajuste técnico

### Problema identificado

Durante las primeras pruebas se necesitaba mejorar la detección de los límites del dohyo y equilibrar la velocidad de los motores. Una diferencia entre las lecturas de los sensores o entre las velocidades de los motores puede provocar respuestas incorrectas durante el combate.

### Cambio realizado

Se ajustó la lógica de detección mediante umbrales y se modificaron los valores de calibración de los motores.

**Calibración final de motores:**

```cpp
// ---------------- CALIBRACION DE MOTORES (MÁS VELOCIDAD) --------------
const int CALIB_L = 160;
const int CALIB_R = 107;
```

También se verificó el funcionamiento del código de detección por umbral, el cual respondió correctamente durante las pruebas realizadas.

### Resultado esperado

- Mejorar la respuesta ante los límites del dohyo.
- Reducir las diferencias de velocidad entre los motores.
- Evitar que el robot continúe avanzando cuando detecte una superficie correspondiente al borde.
- Conseguir un comportamiento más estable durante el desplazamiento.

## 4. Evolución del robot: V1 – K1 – K2

| Versión | Cambios principales | Resultado |
|---|---|---|
| V1 | Primera versión del código y configuración inicial del robot. | Se estableció la lógica básica de movimiento y detección. |
| K1 | Modificaciones realizadas a la lógica de búsqueda y combate. | Se mejoró la organización del comportamiento del robot. |
| K2 | Ajuste de umbrales de los sensores QTR-1RC y calibración de motores. | Se comprobó la detección por umbral y se establecieron nuevos valores para los motores. |

### Configuración K2

| Parámetro | Valor |
|---|---:|
| CALIB_L | 160 |
| CALIB_R | 107 |
| Sensor de borde izquierdo | QTR-1RC |
| Sensor de borde derecho | QTR-1RC |
| Detección de borde | Mediante umbral |
| Estado del código de detección | Funcionando |

Los cambios de K2 se enfocaron principalmente en mejorar la detección de borde y ajustar el movimiento del robot. No se cuenta con un registro numérico comparable de todas las versiones anteriores, por lo que la evolución se documenta a partir de los cambios realizados.

## 5. Pruebas de sensores y robustez

### 5.1 Mediciones de sensores QTR-1RC

Se realizaron mediciones con ambos sensores sobre superficies negras y blancas. Los valores obtenidos fueron los siguientes:

**Superficie negra**

| Prueba | Sensor izquierdo (µs) | Sensor derecho (µs) |
|---:|---:|---:|
| 1 | 2500 | 1828 |
| 2 | 2500 | 1800 |
| 3 | 2500 | 1908 |
| 4 | 2500 | 1908 |
| **Promedio** | **2500** | **1861** |

**Superficie blanca**

| Prueba | Sensor izquierdo (µs) | Sensor derecho (µs) |
|---:|---:|---:|
| 1 | 1260 | 244 |
| 2 | 1092 | 248 |
| 3 | 924 | 240 |
| 4 | 932 | 248 |
| **Promedio** | **1052** | **245** |

### 5.2 Interpretación de resultados

Las mediciones muestran una diferencia entre las lecturas de las superficies blancas y negras. Esto permite establecer un umbral para distinguir ambas condiciones.

También se observa que los sensores no presentan exactamente los mismos valores, por lo que es importante considerar cada lectura de manera independiente al configurar la detección.

El código de detección por umbral funcionó correctamente durante las pruebas, por lo que se considera que el ajuste realizado permite continuar con la integración del sistema.

### 5.3 Pruebas de sensores infrarrojos JS40F

Para revisar la detección del oponente se consideraron diferentes distancias de referencia. Los resultados de esta tabla son valores estimados para documentar el comportamiento esperado y deben validarse mediante mediciones físicas.

| Distancia | Sensor izquierdo | Sensor derecho | Respuesta esperada |
|---:|---|---|---|
| 10 cm | Detecta | Detecta | Detección de oponente |
| 20 cm | Detecta | Detecta | Detección de oponente |
| 30 cm | Detecta | Detecta | Detección de oponente |
| 35 cm | Detecta | No detecta | Detección parcial |
| 40 cm | No detecta | No detecta | Sin detección |

Los sensores JS40F trabajan mediante una salida digital, por lo que su respuesta indica la presencia o ausencia de un objeto dentro de su rango de detección. La distancia efectiva puede cambiar dependiendo del material, tamaño y orientación del objeto.

### 5.4 Prueba de robustez

Se revisó la respuesta de los sensores de borde ante las dos superficies utilizadas durante la calibración.

| Condición | Resultado |
|---|---|
| Superficie negra | Lecturas diferenciables de las obtenidas sobre blanco. |
| Superficie blanca | Lecturas diferenciables de las obtenidas sobre negro. |
| Detección mediante umbral | Funcionamiento correcto durante las pruebas. |
| Respuesta de ambos sensores | Se identificaron diferencias entre sus valores, por lo que se consideran umbrales individuales. |

La prueba permitió comprobar que existe una diferencia suficiente entre las lecturas para trabajar con una condición de detección por umbral. Sin embargo, todavía es necesario validar el comportamiento del robot en diferentes posiciones y durante movimientos reales dentro del dohyo.

## 6. Preparación para la demostración

Durante esta sesión se realizaron ajustes para dejar el sistema en mejores condiciones para una demostración posterior.

Los aspectos revisados fueron:

- Funcionamiento del código de detección de borde.
- Lecturas de los sensores QTR-1RC.
- Calibración de los motores.
- Funcionamiento de los sensores infrarrojos de detección de oponente.
- Integración de los ajustes dentro del código principal.

### Estado de preparación

| Elemento | Estado |
|---|---|
| Código principal | Revisado |
| Detección de borde | Funcionando mediante umbral |
| Calibración de sensores QTR-1RC | Realizada |
| Calibración de motores | Actualizada |
| Sensores JS40F | Requieren validación física de alcance |
| Prueba completa de combate | Pendiente |
| Demostración final | Pendiente |

## 7. Gate E4 — Evaluación del día

| Criterio | Estado | Observación |
|---|---|---|
| Código revisado | Cumplido | Se revisó la lógica general del sistema. |
| Sensores de borde calibrados | Cumplido | Se registraron lecturas en blanco y negro. |
| Detección por umbral | Cumplido | El código respondió correctamente. |
| Motores calibrados | Cumplido | Se actualizaron los valores de ambos motores. |
| Sensores de oponente validados | Pendiente | Falta comprobar físicamente las distancias de detección. |
| Prueba completa de combate | Pendiente | Se necesita realizar una prueba integral en el dohyo. |
| Preparación de demostración | En proceso | Se cuenta con ajustes importantes, pero falta validar el comportamiento completo. |

### Decisión del Gate

**Resultado: CON RESTRICCIONES.**

El equipo logró avanzar en la calibración de los sensores de borde y en el ajuste de los motores. Las lecturas obtenidas permiten distinguir entre superficies blancas y negras, y el código de detección por umbral ya funciona correctamente.

Sin embargo, todavía es necesario comprobar el alcance real de los sensores infrarrojos y realizar pruebas completas de movimiento y combate. Por esta razón, el robot presenta avances importantes, pero aún requiere validación antes de considerarse listo para la demostración final.

## 8. Conclusión del día

Durante el cuarto día de trabajo nos enfocamos principalmente en probar el código y calibrar los sensores del minisumo. Uno de los avances más importantes fue conseguir que el sistema de detección por umbral funcionara correctamente, ya que esto permite identificar con mayor claridad cuándo el robot se encuentra sobre una superficie diferente a la del dohyo.

También realizamos ajustes en la calibración de los motores, utilizando valores diferentes para el lado izquierdo y derecho. Esto es importante porque ambos motores no necesariamente responden de la misma manera y es necesario compensar esas diferencias para conseguir un movimiento más equilibrado.

Las mediciones de los sensores QTR-1RC nos ayudaron a conocer mejor su comportamiento sobre superficies blancas y negras. Aunque todavía falta realizar pruebas más completas con el robot en movimiento, los resultados obtenidos representan un avance para continuar con la integración del sistema.

Para la siguiente sesión será importante validar el alcance de los sensores infrarrojos, probar el comportamiento de búsqueda y ataque y realizar pruebas completas dentro del dohyo. De esta manera podremos comprobar que los ajustes realizados funcionan correctamente cuando todos los componentes trabajan al mismo tiempo.

## 9. Evidencias

Las fotografías y videos de las actividades, mediciones y pruebas realizadas durante la sesión se encuentran en la carpeta compartida del equipo.

**Evidencias correspondientes al 29 de octubre de 2026:**
- Pruebas de lectura de los sensores QTR-1RC.
- Mediciones sobre superficies blancas y negras.
- Ajustes de calibración de motores.
- Pruebas del código de detección por umbral.
- Registro del trabajo realizado durante la sesión.
