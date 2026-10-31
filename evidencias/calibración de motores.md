# Calibración de motores

## Calibración 1

https://github.com/user-attachments/assets/2ccb9ce1-bbdc-4cc9-8cc9-792a8308b71c

## Calibración 2

https://github.com/user-attachments/assets/61904189-8437-4317-b82d-b64525079021

## Calibración 3

https://github.com/user-attachments/assets/56cbe535-7cd0-4f23-b768-1bea39917e4a

### Conclusiones
Tras realizar las pruebas experimentales con la placa **XMotion V3**, se identificó una asimetría mecánica/eléctrica en la tracción de los motores, donde la plataforma tendía a desviarse originalmente hacia la izquierda debido a una menor respuesta del motor derecho.

Para corregir esta deriva y garantizar un avance recto perfecto al solicitar el 100% de velocidad (`driveCalibrated(100, 100)`), se estableció experimentalmente una **proporción de calibración de 20 a 30 (relación 2:3)**:

* **Motor izquierdo (`CALIB_R = 20`):** Ajustado a una potencia máxima de **20 / 255**.
* **Motor derecho (`CALIB_L = 30`):** Ajustado a una potencia máxima de **30 / 255**.

Esta compensación otorga un **50% más de potencia relativa al motor derecho**, equilibrando la fricción de la reductora y logrando la trayectoria rectilínea necesaria para la embestida autónoma.
