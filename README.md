# P1-VC
### Tarea 2: Composición estilo Mondrian

En este ejercicio se usan las funciones de la librería OpenCV para crear una composición abstracta estilo Mondrian sobre una imagen de 600 x 600 píxeles. Primero, se inicializa un fondo blanco puro utilizando matrices de NumPy. A través de las funciones `cv2.rectangle()` y `cv2.line()`, se dibujan líneas y rellenos de colores primarios (rojo, amarillo y azul).

A las funciones se le pasan la imagen, las coordenadas de comienzo y final del dibujo, el color (en formato RGB) y el grosor. En el caso de los rectángulos, se le pasa un grosor de `-1` para que la figura se rellene de color sólido, mientras que a las líneas negras se les aplica un grosor de `8`. De esta manera, se van formando las figuras con unas pocas llamadas a las funciones.



