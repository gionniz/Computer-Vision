
# Práctica Trabajo Final - Curso 2023/2024

### Link
El codigo y el material utilizado està disponibile en github al link:  
Doc MediaPipe  
https://developers.google.com/mediapipe/solutions/vision/hand_landmarker  
https://developers.google.com/mediapipe  

Codigo  
[GitHub - gionniz](https://github.com/gionniz/Computer-Vision/tree/main/P5 "GitHub gionniz")

### Autores
Trabajo realizado por:
- **Giovanni Sgambato** y **Agata Cavigioli**

# Documento de memoria
Motivación/argumentación del trabajo  
Objetivo de la propuesta  
Descripción técnica del trabajo realizado  
Fuentes y tecnologías utilizadas  
Conclusiones y propuestas de ampliación  
Indicación de herramientas/tecnologías con las que les hubiera gustado contar  
Créditos materiales no originales del grupo  

# Motivación/argumentación del trabajo
La practica propone que se realize una implementacion que haga uso de algunas herramientas presentadas en clase de la asignatura de **Vision por Computador** (enero 2024), 
las cuales nos permiten trabajar en tareas de **detección y reconocimiento facial**. 
familiarizarse con la librería de Mediapipe, en concreto, usar la detección de manos para poder usar gestos codificados en un juego.


# Objetivo de la propuesta

![image](https://github.com/gionniz/Computer-Vision/assets/2800642/2799163e-9789-470e-906f-32d395b12f20)

El principal objetivo de este proyecto es de realizar un proyecto que integre técnicas de Visión por Computador vista en clase,
familiarizarse con la librería de Mediapipe y usar tecnicas de deteccion detección de manos para realizar un simple juego interactivo.

# Descripción técnica del trabajo realizado

Una vez preparada el entorno con las librerías necesarias, hay que importar las librerías e iniciar la webcam (como se ha hecho visto en proyectos anteriores).

El siguiente paso consiste en utilizar la librería Mediapipe para la "captura" de manos y dedos.
El módulo hands de mediapipe realiza la detección de las manos, mientras que el módulo de dibujo se utiliza para mostrar reultados en frame.
(dibuja esqueleto y key de la mano). 

Luego hay que crear una instancia de la clase manos y proporcionar algunos parametros 
(valores de confianza mínima de detección y confianza mínima de seguimiento).  

Ahora utilizamos el frame recibido de opencv para capturar objetos y llamamos al proceso hands. 
Esto devolverá un objeto de resultados "multi hand landmarks" que contiene todos los detalles de las manos detectadas en la imagen.
Ejecútandolo a través del módulo de dibujo se obtiene una imagen. 
Ahora Mediapipe nos está dando toda esta información, las posiciones xy de cada uno de los puntos de esta imagen. 

Tenemos tres configuraciones. 
piedra = en este caso, los cinco dedos están cerrados. 
papel = los cinco dedos están abiertos. 
tijeras = los dedos índice y corazón están abiertos y los demás cerrados.

Básicamente, lo que tenemos que hacer para este ejercicio es hacer un control del estado de cada uno de nuestros dedos , si ¿Están abiertos o cerrados? 

Por ejemplo si Tomemos el dedo índice. 
Primero, podemos ver que Mediapipe nos da tres puntos a lo largo del dedo índice:



Planear el juego
Con la tecla barra de epacio e empieza un round y un timer

un flag booleano de etado nos dice si el ssitema eta ready o in attesa

![image](https://github.com/gionniz/Computer-Vision/assets/2800642/f6146dde-c3a5-4fd4-b819-2ed73125dc17)
