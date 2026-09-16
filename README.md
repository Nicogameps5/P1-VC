# Practica 1 VC

## Tarea 1: Tablero de Ajedrez
### Forma manual:
Para generar el tablero de ajedrez se inicializa la matriz de 800×800 píxeles con un único canal en negro mediante `np.zeros()`. A continuación, se emplean dos bucles for anidados para iterar en saltos de 100 píxeles a lo largo de las filas y columnas para rellenar los cuadrados que corresponderian a las casillas blancas dentro del bucle. La condición `(i // tamaño + j // tamaño) % 2 == 0` evalúa la paridad de la coordenada de cada casilla para determinar que corresponda con una casilla blanca y pintar de blanco (255) las regiones correspondientes. Finalmente, la imagen resultante se renderiza en pantalla en escala de grises utilizando `plt.imshow` y se despliega con `plt.show()`.
![alt text](image.png)

### Con asistente IA:
El asistente IA genera el tablero de ajedrez de forma vectorizada y sin bucles explícitos. Define en primer lugar una matriz bidimensional de 2×2 mediante `np.array(..., dtype=np.uint8)` que contiene la alternancia inicial entre blanco (255) y negro (0). A continuación, emplea la función `np.tile(patron_base, (4, 4))` para replicar dicho bloque cuatro veces en cada eje y conformar la cuadrícula lógica de 8×8 celdas. Seguidamente, escala cada casilla al tamaño deseado de 100×100 píxeles calculando el producto tensorial de Kronecker con `np.kron()`, multiplicando la matriz del tablero por un bloque de unos generado con `np.ones((100, 100), dtype=np.uint8)` para alcanzar una resolución total de 800×800 píxeles.
![alt text](image-1.png)

Al hacerlo de forma manual el codigo es mas intuitivo, ya que recorre la matriz celda a celda con dos bucles `for` y pinta las casillas blancas que correspondan, pero requiere más código y es algo más lenta al ejecutarse en Python puro. Por contra, la solución con IA es más compacta y eficiente, ya que resuelve el tablero en apenas tres líneas usando `np.tile` y `np.kron` para generar y escalar el patrón sin ningún bucle, pero es mas complicada de  entender.



## Tarea 2: Composición estilo Mondrian

En este ejercicio se usan las funciones de la librería OpenCV para crear una composición abstracta estilo Mondrian sobre una imagen de 600 x 600 píxeles. Primero, se inicializa un fondo blanco puro utilizando matrices de NumPy. A través de las funciones `cv2.rectangle()` y `cv2.line()`, se dibujan líneas y rellenos de colores primarios (rojo, amarillo y azul).

A las funciones se le pasan la imagen, las coordenadas de comienzo y final del dibujo, el color (en formato RGB) y el grosor. En el caso de los rectángulos, se le pasa un grosor de `-1` para que la figura se rellene de color sólido, mientras que a las líneas negras se les aplica un grosor de `8`. De esta manera, se van formando las figuras con unas pocas llamadas a las funciones.



