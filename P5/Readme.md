# Práctica VC_P5 - Reconocimiento de matrículas - Curso 2023/2024
Esta practica de la asignatura de **Vision por Computador** (nov 2023) tiene el objetivo de desarrollar un prototipo de sistema que identifique la matrícula de un vehículo a partir de imágenes (o video).  

### Link
El codigo y el material utilizado està disponibile en github al link:  
[GitHub - gionniz](https://github.com/gionniz/Computer-Vision/tree/main/P5 "GitHub gionniz").

### Autores
Trabajo realizado por:
- **Giovanni Sgambato** y **Agata Cavigioli**

## Motivacion del trabajo
La detección de vehículos y la extracción eficiente de matrículas a partir de imágenes son elementos cruciales en los sistemas de vigilancia, seguridad vial y gestión del tráfico.  
Esta propuesta responde a la necesidad de desarrollar un sistema capaz de identificar coches y extraer sus matrículas de forma precisa y rápida,  
esencial para automatizar los procesos de vigilancia y control de vehículos.  

El objetivo es proporcionar una solución robusta que permita el reconocimiento y registro de vehículos en entornos complejos mediante **YOLOv8**, 
un algoritmo de detección de objetos, y posteriormente extraer las matrículas de estos vehículos mediante técnicas de **procesamiento de imágenes** y **reconocimiento óptico de caracteres** (OCR).   

Se realizaron 2 intentos de detectores:
- **Detector 1**: utilizando tecnicas de procesamiento de la imagen
- **Detector 2**: utilizando ML y entrenando un nuevo modelo que detecte las matrículas como nueva clase de YOLO.

## Descripcion tecnica del trabajo realizado
### Detector 1
**Implementación de YOLO para la detección de coches**  
La implementación de YOLO (You Only Look Once) se basa en un modelo pre-entrenado capaz de detectar diversos objetos incluyendo vehículos, en imágenes.  
Esta técnica permite identificación precisa de coches dentro de un conjunto diverso de objetos.  
La primera parte del proyecto consiste en detectar un coche en una imagen y separarlo del fondo con un típico rectángulo de segmentación.

**Primer intento de extracción de matrículas de vehículos**  
La metodología utilizada para la extracción de matrículas se basa en técnicas de procesamiento de imágenes y detección de contornos.  
Esta etapa tiene como objetivo aislar y segmentar las matrículas de los vehículos detectados para su sucesiva análisis.  
Una vez detectados los vehículos, la etapa siguiente consiste en procesar las regiones de interés (ROI) que contienen los vehículos para extraer las matrículas,
en en particular la parte inferior de la imagen.  
Se exploraron técnicas como la segmentación de imágenes, la detección de contornos y el procesamiento basado en regiones para aislar y extraer la información.
Sin embargo, este enfoque inicial se enfrentó a dificultades para extraer con precisión matrículas debido a las variaciones en la iluminación, pose y calidad de la imagen.  

![image](https://github.com/gionniz/Computer-Vision/assets/2800642/b76c337d-04e7-48ea-b819-7e98cee8bef7)

**Segundo intento de extracción de matrículas de vehículos**
En el segundo intento, la atención se centró en un enfoque perfeccionado para la extracción de matrículas tras la detección de vehículos, con una estrategia revisada más detallada y exhaustiva.
Se realizaron optimizaciones en el proceso de selección de contornos aplicando técnicas avanzadas de procesamiento de imágenes,  
como la conversión a escala de grises, el umbral, la detección de bordes (que mejoró mucho el resultado final), la detección de contornos y el filtrado por zonas, para localizar y aislar con mas precisión.  

![image](https://github.com/gionniz/Computer-Vision/assets/2800642/edcaa760-428b-4f9a-8c57-66794c395f5c)

**Reconocimiento de texto con Tesseract OCR**
La integración de Tesseract OCR permite reconocer y extraer el texto presente en las matrículas identificadas.  
A pesar de los retos inherentes a la variedad de formatos y condiciones de las matrículas, esta herramienta ofrece una solución versátil para la identificación de texto.  

![image](https://github.com/gionniz/Computer-Vision/assets/2800642/546e6202-fbaf-4f5e-8470-ae7cc4afac06)

### Detector 2
## Modelo Yolo Custom
En esta fase, nuestro enfoque se apartó del proceso manual, en su lugar, nos adentramos en el entrenamiento de un detector personalizado utilizando YOLOv8.  
Para iniciar el entrenamiento, comenzamos con la anotación de imágenes, la utilización de un conjunto de datos de Roboflow, que incluía 200 imágenes de matrículas preetiquetadas, simplificó nuestra tarea.  
Con el conjunto de datos perfectamente organizado en carpetas de entrenamiento, validación y prueba, exportarlo al formato YOLOv8 fue sencillo y una vez compiladas las imágenes y las anotaciones, creamos un archivo .yaml,  
para el entrenamiento.  

![image](https://github.com/gionniz/Computer-Vision/assets/2800642/457c3d0c-c899-42db-9ecb-4d80a60c8098)

Este archivo definía parámetros esenciales como los directorios de entrenamiento, validación y prueba, junto con los nombres de las clases y el número de clases. 
Tras un entrenamiento satisfactorio, un resumen visual mostraba la reducción de la función de pérdida y la mejora de la precisión por época. 

![image](https://github.com/gionniz/Computer-Vision/assets/2800642/990a690e-2281-4711-a2c4-9a09cf5896c0)

Una vez completado el entrenamiento, introdujimos la placa modelo en nuestro detector entrenado para detectar matrículas.
A continuación, formulamos una función de detección para identificar y mostrar hábilmente matrículas en imágenes de vehículos.

![image](https://github.com/gionniz/Computer-Vision/assets/2800642/fcfad9c9-91ec-4e05-baeb-8abcf897e2ec)


## Fuentes y tecnologias utilizadas
Se emplearon diversas tecnologías y herramientas,
**OpenCV** para el procesamiento de imágenes, **YOLO** para la detección de objetos y **Tesseract OCR** para el reconocimiento óptico de caracteres.

## Conclusiones y propuestas de ampliacion
Los resultados obtenidos en la detección de vehículos y la extracción mostraron una eficacia considerable a la hora de identificar matrículas en diversas condiciones.  
Sin embargo, se identificaron áreas de mejora para aumentar la precisión y el rendimiento del sistema en entornos más más difíciles.  
La integración de algoritmos de postprocesado podría aumentar la precisión en la identificación de matrículas.  
Otra vía de investigación interesante podría ser trabajar con vídeo en lugar de imágenes.  

## Otras Referncias

https://www.cnet.com/a/img/resize/mission-impossible-dead-reckoning-fiat-500.jpg  
https://inside-machinelearning.com/en/yolov8-how-to-use/  
https://inside-machinelearning.com/en/bounding-boxes-python-function/  
https://blog.roboflow.com/how-to-train-yolov8-on-a-custom-dataset  
