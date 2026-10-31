# Demostración Kaizen — Día 5

**Plataforma:** M01 — Mini-sumo autónomo (XMotion V3)  
**Objetivo técnico de la demostración:** Demostrar el funcionamiento del minisumo mediante su estrategia de búsqueda y defensa, detección de borde con sensores QTR-1RC y sistema de arranque. El criterio de éxito fue completar el combate y conseguir la victoria.  
**Versión candidata:** K2 — versión final ajustada durante el Día 5. Commit/tag pendiente de registrar.

## Guion de 90 segundos por estudiante

### Juan Arturo López Delgado

1. **Al llegar, yo todavía no podía…** integrar y comprobar todos los ajustes del robot para que funcionara correctamente en las condiciones reales del dohyo.
2. **Mi alcance y mi principal dificultad fueron…** trabajar en la máquina de estados de combate, la recuperación de borde y la estrategia de búsqueda. Una de las dificultades fue adaptar los sensores QTR-1RC a un dohyo diferente.
3. **Cambié o construí…** mejoré la estrategia defensiva, ajusté el código de detección por umbral y participé en la implementación del arrancador. Como el puerto original no funcionaba, lo conectamos en OTR (A1) y realizamos la soldadura necesaria.
4. **Las pruebas muestran…** que los sensores QTR-1RC presentaron diferencias claras entre sus lecturas altas y bajas. Además, durante la demostración el robot funcionó correctamente y consiguió ganar el combate.
5. **Ahora puedo…** ajustar la estrategia de combate, calibrar sensores de borde para diferentes superficies e integrar soluciones de hardware cuando una conexión no funciona como se esperaba.

### Melissa Zúñiga Miranda

1. **Al llegar, yo todavía no podía…** comprobar el funcionamiento completo del robot con todos sus componentes integrados y las condiciones del dohyo de la demostración.
2. **Mi alcance y mi principal dificultad fueron…** trabajar en la motorización, la máquina de estados y los sensores de borde, especialmente conseguir que el robot respondiera correctamente después de los cambios de calibración.
3. **Cambié o construí…** participé en los ajustes finales del código, la revisión de los sensores QTR-1RC y las pruebas de funcionamiento antes del combate.
4. **Las pruebas muestran…** que fue necesario recalibrar los sensores para el nuevo dohyo y que, después de los ajustes, el robot funcionó correctamente durante la demostración y ganó el combate.
5. **Ahora puedo…** participar en la calibración e integración de los sistemas del minisumo y comprobar su funcionamiento antes de una demostración.

## Evidencia de la demostración

| Alcance | Responsable | Archivo o enlace | Resultado | Qué aprendió |
|---|---|---|---|---|
| MS08 — FSM de combate | Juan Arturo López Delgado | Código final y video de demostración en carpeta compartida | El robot ejecutó su estrategia durante el combate y obtuvo la victoria. | La lógica de combate debe adaptarse a las condiciones reales de operación. |
| MS11 — Recuperación de borde | Juan Arturo López Delgado | Mediciones QTR-1RC y código de detección por umbral | Se obtuvieron lecturas diferenciables y funcionó la detección de borde. | Es necesario recalibrar los sensores cuando cambia la superficie del dohyo. |
| MS09 — Estrategia de búsqueda | Juan Arturo López Delgado | Código final y video de demostración en carpeta compartida | Se integraron ajustes a la estrategia de búsqueda y defensa. | La estrategia debe considerar tanto la detección del oponente como la protección del robot ante los bordes. |
| MS03 — Motorización | Melissa Zúñiga Miranda | Código de calibración y evidencias de pruebas | Se conservaron los ajustes de calibración de los motores para el funcionamiento final. | Las diferencias entre motores deben considerarse para conseguir un movimiento equilibrado. |
| MS08 — FSM de combate | Melissa Zúñiga Miranda | Código final y video de demostración en carpeta compartida | El sistema integrado funcionó durante el combate. | La integración de los diferentes comportamientos es importante para que el robot responda correctamente. |
| MS05 — Sensores de borde | Melissa Zúñiga Miranda | Registro de lecturas QTR-1RC y evidencias de calibración | Los sensores respondieron con diferencias claras entre las condiciones registradas. | La calibración debe realizarse con las condiciones del dohyo donde se utilizará el robot. |
| Sistema de arranque | Equipo Jamón | Fotografías y video de la conexión en carpeta compartida | Se implementó en OTR (A1) mediante una conexión soldada y funcionó durante la demostración. | Es importante identificar conexiones alternativas cuando un puerto presenta fallas. |

## Aprendizajes colectivos / próximos pasos hacia Robolympics

Durante el proyecto aprendimos que no basta con conseguir que el código funcione en una primera prueba, sino que también es necesario comprobarlo con las condiciones reales donde se utilizará el robot. Un ejemplo fue el cambio de dohyo, que nos obligó a realizar nuevamente la calibración de los sensores QTR-1RC.

Otro aprendizaje importante fue la solución del problema del arrancador. Al no funcionar el puerto que habíamos utilizado inicialmente, buscamos otra conexión disponible, OTR (A1), y realizamos la soldadura para poder implementarlo. Esto nos permitió completar el sistema y comprobar su funcionamiento durante la demostración.

También mejoramos la estrategia defensiva y terminamos de ajustar el código. El resultado más importante fue que el minisumo funcionó correctamente durante el combate y consiguió la victoria.

Como próximos pasos hacia Robolympics, sería conveniente realizar más enfrentamientos contra diferentes robots, comprobar la estabilidad de la estrategia defensiva, medir los tiempos de respuesta de los sensores y verificar que la calibración siga funcionando en distintos dohyo. También sería útil documentar mejor las conexiones y conservar una versión estable del código para futuras pruebas.

El principal aprendizaje colectivo fue entender que la mejora de un robot requiere probar, detectar problemas, realizar cambios y volver a comprobar los resultados. La victoria en la demostración fue un buen resultado, pero todavía podemos mejorar la robustez y consistencia del minisumo para futuras competencias.
