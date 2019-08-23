# Biblioteca Pandas

La biblioteca pandas está construida sobre NumPy, por lo que aprovecha toda su eficiencia. Con ella vas a poder cargar tus datasets fácilmente y realizar el análisis exploratorio. Es una biblioteca indispensable en el workflow de Data Science.

series: es un array con un indice

documentacion:
https://pandas.pydata.org/pandas-docs/stable/user_guide/indexing.html



## Apply

Con Numpy podemos aplicar operaciones vectoriales.
Con Pandas, podemos usar apply para lo mismo.
Le pasamos un data frame, columnaxcolumna o filaxfila, es decir, le aplicamos una funcion a una fila.


## ApplyMap

Cuando queremos aplicar una operacion a cada uno de los elementos del Data Frame.


si queremos aplicar a cada uno de los elementos.

Por cada elemento  en x, aplicale la operacion:

> usuarios_df.applymap(lambda x: x/2)


# Filtrando valores faltantes

## isna()

isna, nos muestra si un dato esta faltando.

Generalmente en el DataFrame o tabla viene un valor como `NaN`.

Con este comando nos devolvera la misma tabla pero con `True/ False`.


## dropna()

Obtendremos las filas que tienen valores, las que tengan `NaN` seran descartadas.


Pero si queremos descartar solo los valores nulos en un lugar en particular, utilizamos un parametro.
Ej, descartar edad.

> usuarios.dropna(subset=['edad'])



# Completando valores

Como rellenar valores faltantes.


## fillna()

CUIDADO, hay que indicar donde se debe agregar, ya que podria agregar en lugares no deseados.

Ejemplo, para agregar los valores faltantes en la columna *edad*:

> copia_df['edad'].fillna(usuarios.edad.mean())


Tambien podemos rellenar los espacios faltantes con un valor por default, por ejemplo con Cero.

> copia_df.fillna(0)


si nosotros colocamos un `inplace= True` modificamos el DataFrame original, y no la copia generada (automaticamente) por el editor.



# Descartar valores

## drop_duplicates()

Por ejemplo borrar aquellos datos de 20 años con datos nulos.
Puede haber varios usuarios de 20 años pero borraremos aquellos que tengan datos nulos.

O bien, si queremos borrar todos excepto el ultimo dato:

> usuarios_df.drop_duplicates(subset=['edad'], keep='first')














