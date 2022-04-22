## Prueba de Ji cuadrada :pencil2:

La prueba de Ji cuadrada es una prueba de hipótesis propuesta por Pearson que permite contrastar la hipótesis de que los dos criterios de clasificación utilizados (las dos variables categórcias) son independientes.

Para ello las frecuencias observadas (las frecuencias de hecho obtenidas) con las frecuencias esperadas (las frecuencias que teóricamente debería haber en cada casilla si los dos criterios de clasificación fueran independientes)

Para realizar una prueba de Ji cuadrada utilizando el lenguaje de programación R recomiendo el uso del siguiente código;

Nota: Para todo el código los datos que estén "entre comillas" son los que debes sustituir por tus propios datos.

1. La pruebas parte de tablas de contingencia, para formarlas utiliza el siguiente código;
~~~
"Nombre de la tabla de contingencia" <- matrix(c("colores separados por comas", "datos empezando de arriba a abajo de izquierda a derecha"),"número de filas", "número de columnas")
~~~
2. Código para introducir la prueba de Ji cuadrada
~~~
"Nombre1"<-chisq.test("nombre de la tabla de contingencia")
~~~
3. Listar los objetos en la memoria
~~~
ls("Nombre1")
~~~
4. Cargar la librería "MASS" para tener acceso a bases de datos
~~~
library(MASS)
~~~
5. Realizar análisis de correspondencia
~~~
"Nombre2"<-corresp("nombre de tabla de contingencia")
~~~
6. Creación del gráfico
~~~
plot(c("nombre2"$rscore),rep(0,"número de filas"),type=”n”,xlim=c("-2,2"), main=”Título de la Gráfica”)
plot(c("nombre2"$cscore),rep(0,"número de columnas"),type=”n”,xlim=c("-2,2"), main=”Título de la Gráfica”)
text(c("nombre2"$rscore),rep(0,"número de filas"), labels=c(“nombres de una de las variables dentro del grafico), col=" "firebrick2" ")
text(c("nombre2"$cscore),rep(0,"número de columnas"), labels=c(“nombres de las otras variables dentro del grafico), col=" ”mediumblue” ")
~~~
