# Práctica VC_P6 - Análisis facial - Curso 2023/2024

La practica propone que se realize una implementacion que haga uso de algunas herramientas presentadas en clase de la asignatura de **Vision por Computador** (nov/dec 2023), 
las cuales nos permiten trabajar en tareas de **detección y reconocimiento facial**. 

En tal proposito se han realizado 2 propuestas:  

* **1)** En el primer ejercicio de reconocimiento facial 
se utiliza **DeepFace** para analizar una imagen adquirida mediante upload o webcam.  
Esta herramienta permite **analizar la imagen** y detectar características del sujeto de la imagen como: **sexo, edad, raza y expresión facial** (como aproximación a la emoción que manifiesta).  
Además, en la segunda parte es posible realizar una **identificaccion** de un sujeto, comparando 2 imágenes adquiridas para evaluar y verificar si los sujetos de las fotos son la misma persona.  
![image](https://github.com/gionniz/Computer-Vision/assets/2800642/6da9c78f-28ab-4e5e-8d71-d57960ca923a)


* **2)** En el seguendo ejercicio se quiere **reconocer un sujeto** (identificado en una imagen con el solo) **buscandolo en otra imagen de grupo**,  
utilizando DeepFace y RetinaFace (para deteccion de caras en imagene "crowded".
![image](https://github.com/gionniz/Computer-Vision/assets/2800642/f37f57d0-2987-4da0-bdfc-25c9b7266d18)


### Link
Los  2 ejercicios están disponibles y ejecutables en un cuaderno Colab en el siguiente enlace:  
[Colab - Práctica VC_P6 - Analisis Facial](https://colab.research.google.com/drive/1s6ZkMi4MZ_Ra3Z641XG8r5A54nEaeCZ4#scrollTo=5zcyeV0QDGt3 "Práctica VC_P6 - Analisis Facial").

El material utilizado està disponibile en github al link:  
[GitHub - gionniz](https://github.com/gionniz/Computer-Vision/tree/main/P6 "GitHub gionniz").

### Autores
Trabajo realizado por:
- **Giovanni Sgambato** y **Agata Cavigioli**


## Ejercicio 1  
**Parte 1**
- **Paso 1. Subir una imagen**:  
  Es posible utilizar 2 métodos para cargar imágenes para su análisis:
  - **upload** = cargar imágenes guardadas localmente
  - **webcam** = GoogleColab de momento (dic 2023) NO permite utilizar webcam y stream video en tiempo real directamente.  
    Se ha utilizado una solución en la que es posible acceder a la cámara con un **"hack"** y obtener un fotograma.
    Recursos:
    - https://answers.opencv.org/question/231737/videocapture-in-colab/
    - https://colab.research.google.com/notebooks/snippets/advanced_outputs.ipynb#scrollTo=buJCl90WhNfq
    - https://colab.research.google.com/drive/1fwqYCxcgEkWTpIgvdLGzJCSYcMI7c3xF?usp=sharing#scrollTo=xS_KFScRb1gv


- **Paso 2. Analisis del sujeto**: Utilizamos DeepFace para analizar la edad, el género, la raza y las emociones de la persona.
![image](https://github.com/gionniz/Computer-Vision/assets/2800642/26480cc8-ac9f-44e9-9024-f7565e2a0eed)  

**Parte 2**  
- **Verificar identidad**: En la segunda parte la implementacion realizada permite verificar si 2 imagenes entra aquellas adquirisdas contienen la misma persona
![image](https://github.com/gionniz/Computer-Vision/assets/2800642/73d9f98c-56dd-43dd-9363-55a9d940d91a)



## Ejercicio 2
En el segundo ejercicio se ha utilizadp por primero **RetinaFace** para la detección de caras en imágenes caóticas y "crowded", es decir muy llena de sujetos.  
Sucesivamente, se utiliza **DeepFace** para verificar y confrontar todas la caras detectadas con otra de referencia.  
El **objetivo** es comparar las caras detectadas con una de otro sujeto de referencia (en una imagen diferente) y **reconcer a la persona correcta**.
![image](https://github.com/gionniz/Computer-Vision/assets/2800642/0bc76f19-f0d2-40a7-a97b-43fca1fddbbe)
