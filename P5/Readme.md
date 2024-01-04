# Práctica VC_P5 - Reconocimiento de matrículas - Curso 2023/2024

Esta practica de la asignatura de **Vision por Computador** (nov 2023) tiene el objetivo de desarrollar un prototipo de sistema que identifique la matrícula de un vehículo a partir de imágenes (o video).  
Para este propósito, se proporciona un modelo de detección de objetos, **YOLOv8**, para la detección de vehículos.  
Además, para el reconocimiento de texto, se ha trabajado con **pytesseract**.  

- **Primer Detector**: Para el primer detector, desglosaremos el proceso de detección de matrículas en tres partes. En primer lugar, nos enfocaremos en la identificación de vehículos en una imagen utilizando el modelo YOLOv8. Una vez obtenidas las detecciones de vehículos, procederemos a realizar un procesamiento en la imagen del vehículo detectado para buscar formas rectangulares, que corresponden a las matrículas. Por último, haremos uso de **pytesseract** para obtener el texto de la matrícula.
- **Segundo Detector**: En este segundo detector, entrenamos nuestro propio modelo basado en **YOLOv8** con el fin de que detecte las matrículas de las imágenes.

### Link
El codigo y el material utilizado està disponibile en github al link:  
[GitHub - gionniz](https://github.com/gionniz/Computer-Vision/tree/main/P5 "GitHub gionniz").

### Autores
Trabajo realizado por:
- **Giovanni Sgambato** y **Agata Cavigioli**


## Primer detector

- **Paso 1. Carga del Modelo YOLO**: Se carga el modelo YOLO previamente entrenado.
- **Paso 2. Detección de Vehículos**: Se realiza la detección de objetos en la imagen utilizando YOLO. Si se encuentra un vehículo, se resalta en la imagen original y se muestra la región de interés alrededor del vehículo.
- **Paso 3. Detección de Matrículas (si se detecta un vehículo)**: Se convierte la región de interés (ROI) alrededor del vehículo a escala de grises y se aplica un umbral. Luego, se buscan los contornos y se filtran aquellos en la mitad inferior de la imagen. Se identifica el contorno más grande, que se asume como la matrícula del vehículo. Se muestra la matrícula y se utiliza Tesseract OCR para reconocer el texto.

A continuación se adjuntan las figuras del proceso descrito:
