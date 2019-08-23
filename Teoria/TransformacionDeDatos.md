# Transformación de Datos


## Features Categoricos

Son Features que no son numericos como un texto. (ej. la colonia de un terreno).


## Features Derivados

Son aquellos que derivan de un feature ya existente.
FEature: Un Tuit, un Feature Derivado: La longitud de ese texto.


# Tecnicas de transformación de Datos


Binning:
Bin: pequeños conjuntos de datos.

Se puede dividir un array de datos en varios grupos con **cut**:

> edades = [20, 22, 25, 27, 21, 23, 37, 31, 61, 45, 41, 32]

> bins = [18, 25, 35, 60, 100]
cats = pd.cut(edades, bins)


Se crean varios grupos, por ejemplo de 18 a 25, hay tres grupos.

```
[(18, 25], (18, 25], (18, 25], (25, 35], (18, 25], ..., (25, 35], (60, 100], (35, 60], (35, 60], (25, 35]]
Length: 12
Categories (4, interval[int64]): [(18, 25] < (25, 35] < (35, 60] < (60, 100]]
```

Con el comando **codes** nos dice a que categoria pertenece, 0,1,2...

> cats.codes

```
array([0, 0, 0, 1, 0, 0, 2, 1, 3, 2, 2, 1], dtype=int8)
```


## Transformacion de datos: Dummies.

Pasar de una variable categorica a una variable numerica.



# SciKit Learn

## Label Encoder

Sirve para normalizar etiquetas.
Teniendo varias clases de datos como Paises o Ciudades, "Paris" o "Tokyo", podemos normalizar su valor con un valor numerico, 0,1...

Tenemos dos funciones muy utilizados:

**fit()** y **transform**.


## OneHotEncoder

Crea una Matriz donde si el dato esta presente pone un **1** y si no pone un **0**.

Primero importamos:

> from sklearn.preprocessing import OneHotEncoder

reshape(): te cambia un vector de vertical a horizontal.



## Imputer

Importamos:

> from sklearn.preprocessing import Imputer

> from numpy import nan
> import numpy as np

Ejemplo, preprocesamiento de datos:

Vamos a rellenar los espacions nulos con el valor promedio de la columna.


```
array([[ nan,		0.,		98.],
		 [	3.,		7.,		99.],
		 [	3.,		5.,		210.],
		 [	4.,		nan,	202.],
		 [	8.,		8.0,	101.]])
```

> imp = Imputer(strategy='mean')
> X2 = imp.fit_transform(X)


```
array([[ 4.5,		0.,		98.],
		 [	3.,		7.,		99.],
		 [	3.,		5.,		210.],
		 [	4.,		5.,		202.],
		 [	8.,		8.0,	101.]])
```


## Pipeline

Etapas, automatizaremos las distintas etapas. Creamos un preprocesamiento uno tras de otro.

Importamos:
Para poder construir el pipeline:
> from sklearn.pipeline import make_pipeline

Para poder escalar datos, es decir, si tenemos datos muy separados, podemos utilizar este StandardScaler para achicar los datos.
> from sklearn.preprocessing import StandardScaler

Imputamos los datos con valores promedio luego usamos el standardScaler para achicarlos.

> pipe = make_pipeline(Imputer(strategy='mean'), StandardScaler())



## Outliers

Son datos que se desvian de los demas datos.

Pueden ser: Univariantes o Multivariantes.
Univariante, se refiere a una sola columna del Data Set.
Multivariante, es cuando depende de multiples columnas, puede no percibirse a simple vista.


## z-score

Se conoce como z-scores a aquellos valores expresados según su desvío estándar de la media. Para entenderlo supongamos un aula.

	* El promedio de edad en ella es de 20 años,
	
	* El desvío estándar es de 5 años

	* y una alumna tiene 35 años.

¿Cuál será el z-score de esta alumna? Para eso tenemos que hacer una pequeña cuenta matemática:

> z = (valor - promedio) / desvío

> z = (35 - 20) / 5 = 3

Basandonos en una tabla de Z-score: http://www.ttable.org/z-score-table.html

En nuestro caso nos dio 3. Sin decimales. Por lo que tenemos que buscar el valor 3 y 0.00.
El valor que encontramos en esta celda es 0.9987. Esto significa que la probabilidad de que alguien tenga menos años que nuestra alumna es del 99.87%.


## Filtrando Outliers por z-score

Ahora que sabemos cómo funciona el z-score, podemos utilizarlo para filtrar outliers en nuestros datos. Para eso basta con determinar un umbral a partir del cual borraremos instancias. En el ejemplo de la alumna de 35 años, podemos decir que es una outlier ya que la probabilidad de que alguien tenga más edad que ella es del 0.13%.

Entonces podemos setear el umbral de z-score en 2. De esta forma borraremos de nuestro dataset a todos los alumnos que tengan 30 años o más.

















