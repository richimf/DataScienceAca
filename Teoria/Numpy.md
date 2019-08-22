# Biblioteca NumPy

Permite trabajar con datos en paralelo, vectores y matrices.

Arreglos en Ceros: `np.zeros`.

Un arreglo de 2x3 de ceros `np.zeros((2,3))`.

Crear un arreglo con un rango del 0 al 10 `np.range(10)`.

> array([0, 1, 2, 3, 4, 5, 6, 7, 8, 9])

O bien `np.arange(10)`.

Crear un arreglo del 1 al 4, pero con valores divididos entre 6 `np.linspace(1,4,6)`.

> array([ 1. ,  1.6,  2.2,  2.8,  3.4,  4. ])


## Slicing

Es un corte de un Array de una dimension.
Para cortar Arrays de dos dimensiones.

Funciona como sigue, se especifica hasta que fila y hasta que columna quieres mostrar `array[fila, columna]`.

```
In:	 arr2d
Out: array([[1, 2, 3],
			[4, 5, 6],
			[7, 8, 9]])
```

Dame solo hasta la fila 1 con la siguiente instrucción `arr2d[:1]`:

```
Out: array([[1, 2, 3]])
```


Dame solo hasta la fila 2 y a partir de la columna 0 con La siguiente instrucción `arr2d[:2, 0:]` o bien `arr2d[:2, :]`:

```
Out: array([[1, 2, 3],
		    [4, 5, 6]])
```

Dame la fila y hasta la columna 2 `arr2d[1, :2]`:

```
Out: array([4, 5])
```

Llenar con un valor en posiciones especificadas utilizando slicing `arr2d[:2, 1:] = 0`, dará como resultado:

```
Out: array([[1, 0, 0],
		    [4, 0, 0],
		    [7, 8, 9]])
```

# Steps

> start:stop:step

Basicamente es un indexado con un paso, siguiendo la syntaxis `x[start:stop:step]`, iremos del valor inicial al final en pasos especificados.

```
x = np.array([0, 1, 2, 3, 4, 5, 6, 7, 8, 9])

// Iremos tomando valores del 1 al 7 de a 2 en 2
// start = 1, stop = 7, step = 2
x[1:7:2]

// El resultado de esto será:
array([1, 3, 5])

```


## Steps negativos

Obtener del penúltimo , hasta el valor 10 `x[-2:10]`.

> array([8, 9])


# Filtros

## Filtros Booleanos

Devuelve un array con valores True o False, dependiendo de la condición especificada.

> arr2d < 2

Para extraer esos valores del array, usamos: `arr2d[arr2d > 0]`.



# Funciones matematicas

np.sqrt()
np.abs()
np.square()
np.add(array1, array2)

Ver mas operaciones en [Math Operations](https://docs.scipy.org/doc/numpy/reference/ufuncs.html).


Obtenemos un promedio de los elementos:

> np.mean(arr) 

O bien:

> arr.mean()

















