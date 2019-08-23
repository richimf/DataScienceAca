# Visualizacion de Datos

## MatplotLib

Permite hacer graficas.


Para comenzar:

> import matplotlib.pyplot as plt

> import numpy as np

creamos un array del 0 al 10, con 100 valores en total:

> x = np.linspace(0, 10, 100)


Creamos figura o entorno para poder graficar:

> %matplotlib inline # mostrar graph en el notebook
> fig = plt.figure()
> plt.plot(x, np.sin(x), '-')
> plt.plot(x, np.cos(x), '--')


Creamos ejes coordenados:

> ax = plt.axes()





## Seaborn

Construido sobre **MatplotLib**, mayor compatibilidad con **Pandas**.

Importando:

> import seaborn as sns


**Histogramas**:

Utilizar `displot`, por defecto ya pone una descripción abajo.

Seaborn tiene la propiedad de dibujar varios graficos sobre el mismo.


**Pair Plots**:

Como visualizar a pares datos.

Cargamos el dataset

> iris = sns.load_dataset("iris")
> print(iris.head())

Ahora iremos comparando atributo por atributo de manera visual.

> sns.pairplot(iris, hue='species', size=2.5)
















