Las preguntas iniciales fueron ¿se puede 
clasificar esa base de datos usando algún modelo
de ML? y ¿cuáles son los parámetros que más 
influyen en la decisión?

Para la segunda pregunta, según la literatura
solo hace falta el vector de velocidad, pero
este conjunto de datos además está tomando
como clase 1 a los flocks y a los agrupamientos.

Lo primero fue la exploración de datos,
la graficación solo toma en cuenta la posición 
de cada partícula, su vector de velocidad y su 
vector de alineación.

A diferencia del modelo de Vicsek, aquí también
está tomando en cuenta cuando hay un agrupamiento,
entonces aunque haya grupos separados pero que
cada uno sigue comportandose como flock, entonces
está etiquetado como flock.
Con esto dicho, hay poblaciones que aunque tengan
una $Psi$ baja, están etiquetados como flock.

Los datos están solo un poco desbalanceados, hay
casi el doble de datos que son de la clase 0 (no
flock) que de la clase 1 (flock/group).
Para compensar el desbalance se hace un 
sobre-muestreo en la clase 1.

A partir de aquí se complican las cosas, hay tres
opciones:
- Tomar todos los atributos tal y como están
- Hacer PCA sobre los datos
- Tomar la varianza de cadad atributo