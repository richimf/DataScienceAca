# Data Science 

## Ambientes de trabajo

Creamos un entorno llamado **ds** 

> conda create --name ds

Aceptamos con `Proceed [Y]`

Luego activamos el entorno:

> source activate ds


Para salir del entorno:

> source deactivate

Para ver nuestros entornos de conda:

> conda info --envs


## Instalando libs en Conda

> conda install pandas

Sale un listado de dependencias del paquete instalado.

Aceptamos con `Proceed [Y]`

> conda install <nombre_paquete>


## Jupyter

En jupyter podemos tener Markdown o Codigo, entre otros.

Una vez instalado Jupyter, entramos desde nuestro entorno:

> jupyter notebook

Los notebooks tienen extensión **.ipynb**

Podemos tener un Jupyter en la consola con:

> ipython


## Comandos mágicos de Jupyter

Ejecutamos un codigo de python en jupyter asi, rapidito:

> %run script.py [enter]

tambien tenemos el comando **len?**, el signo de **?** te dice para que sirve ese comando.

Si querés saber cuanto tiempo tarda en correr tu código podés usar `%time`, `%timeit` y `%%time`.


## Recargar modulos o bien, reiniciar el kernel para codigos que estan referenciados.

> %load_ext autoreload

Al usar autoreload el código se va a actualizar automáticamente y la segunda ejecución de funcion_compleja será la modificada.
