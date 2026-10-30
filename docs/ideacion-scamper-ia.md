# Reporte de Ideación Estructurada (SCAMPER + IA) · Equipo Jamón

- **Equipo:** Jamón
- **Integrantes:** 
  - Juan Arturo López Delgado
  - Melissa Zúñiga Miranda
- **Plataforma:** M01 · Mini-sumo autónomo
- **Alcances seleccionados:** MS08 (FSM Combate), MS09 (Estrategia de búsqueda), MS11 (Recuperación de borde)
- **Marco de Trabajo:** Kaizen Dōjō 2026 — Robollympics (Tec de Monterrey Campus León)
- **Herramienta de IA utilizada:** Gemini 3 Flash / ChatGPT (30 de octubre de 2026)

---

## 1. Identificación y Definición de la Idea Base

- **Solución Actual:** En el archivo de código C++, la función `defenseScan()` ejecuta un pivote alternado en el mismo sitio (`driveCalibrated(-20, 20)` y `driveCalibrated(20, -20)`) cada 10 ciclos para buscar al oponente.
- **Problema:** El giro rotacional estático sobre el propio eje limita el ángulo visual de los sensores JS40F, genera puntos ciegos laterales y hace al robot susceptible a embestidas por la espalda.
- **Valor Deseado:** Aumentar la velocidad de localización del oponente (reducir el tiempo a < 1.2s) sin poner en riesgo la detección del borde con los sensores QTR-1RC ni sobrecargar los motores Jsumo de 750 RPM.

---

## 2. Aplicación de la Técnica SCAMPER (Fase Humana)

1. **[S] Sustituir:** Sustituir el giro estático en el sitio por un barrido en arcos de avance corto alternando tracción diferencial (ej. 25% y 15% PWM).
2. **[A] Adaptar:** Adaptar la función `checkAndEscapeEdge()` para que, además de retroceder, actualice la variable `lastTargetSide` forzando al escaneo a buscar en la dirección opuesta al peligro.
3. **[M] Modificar:** Modificar el contador de ciclos de escaneo (`defenseCounter`) para que varíe la velocidad de giro en caso de no encontrar al rival tras 500 ms.

---

## 3. Integración Crítica de IA Generativa

### Ejemplo de Prompt Enviado
> *"Somos el equipo Jamón en Kaizen Dōjō 2026. Trabajamos en la plataforma M01 Mini-sumo (xMotion V3, motores Jsumo 750 RPM, sensores JS40F y QTR-1RC) con los alcances MS08, MS09 y MS11. Nuestra idea base es mejorar la función `defenseScan()` que gira en sitio de forma simétrica. Aplica SCAMPER (Sustituir, Adaptar, Modificar) para proponer al menos 3 alternativas. Restricciones: 15h semanales totales, hardware existente, seguridad (no salir del dohyō) y una mejora comprobable con la métrica de tiempo de contacto (<1.5s). Indica ventaja, riesgo, requisito y forma de validación. No inventes compatibilidades de hardware."*

### Evaluación Crítica de los Aportes de la IA

| Aporte de la IA | Evaluación Humana / Filtro Técnico | Decisión Tomada |
| :--- | :--- | :--- |
| **1. Escaneo por PWM sinusoidal variable:** Cambiar continuamente la velocidad de giro en forma de onda. | La placa xMotion V3 en C++ tendría picos de consumo innecesarios y retrasos al calcular funciones continuas en bucles rápidos. | **Ajustado:** Se simplificó a saltos discretos de velocidad PWM (25% y 45%). |
| **2. Interrupciones hardware para QTR-1RC:** Muestreo por interrupción para cancelar el escaneo inmediatamente. | Revisando el pinout de nuestro código (`LeftLine = A5`, `RightLine = A2`), los sensores son analógicos/RC y la tarjeta no soporta interrupciones en esos pines. | **Descartado:** Incompatible con la arquitectura de hardware utilizada. |
| **3. Evasión en diagonal con memoria:** Retroceder en ángulo y guardar la dirección de escape en `lastTargetSide`. | Muy viable en software. Utiliza variables existentes en nuestro código (`lastTargetSide`, `lastTargetTime`) para direccionar el robot tras evadir la línea blanca. | **Aceptado:** Se integra directamente en la función `checkAndEscapeEdge()`. |

---

## 4. Elección y Propuesta Final

**Escaneo Adaptativo por Arcos Discretos con Memoria de Borde:**
- **Transformación:** Se combinó la modificación de `defenseScan()` con la adaptación en `checkAndEscapeEdge()`. El robot ahora barre el área en pequeños arcos dinámicos y, si toca la línea blanca, retrocede en diagonal reorientando inmediatamente sus sensores JS40F hacia el centro de la pista.
- **Valor Esperado:** Reducción del tiempo de localización a < 1.2 segundos y erradicación de salidas en reversa por el dohyō.
- **Hipótesis y Prueba:** Realizar 10 corridas cronometradas contra un oponente estático colocado a 45°, 90° y 180°. Se considera exitosa si el tiempo de impacto frontal es < 1.2s y la evasión de borde no presenta fallos.

---

## 5. Reflexiones Auténticas de los Integrantes

- **Juan Arturo López Delgado:**
  > *"La IA me sugirió usar interrupciones por hardware, pero al revisar el esquema técnico de la xMotion V3 en nuestro código me di cuenta de que no era viable; fue nuestro criterio de ingeniería el que rescató el uso de memoria de estado en el retroceso."*

- **Melissa Zúñiga Miranda:**
  > *"La IA asumió que podíamos cambiar la velocidad instantáneamente, pero sabiendo cómo responden los motores Jsumo de 750 RPM ajustamos la propuesta a cambios de PWM discretos para evitar sobrecargar los drivers de la PCB."*

---
*Documento generado para la actividad 'Expandir para mejorar — SCAMPER + IA'. Enlazado desde `docs/entregables/dia-01.md`.*
