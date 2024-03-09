# unab-pandas

``` python
pd.DataFrame(data,
             x,
             y,
             kind,
             ax,
             subplots,
             sharex,
             sharey,
             layout,
             figsize,
             use_index,
             title,
             grid,
             legend,
             style,
             logx,
             logy,
             loglog,
             xticks,
             yticks,
             xlim,
             ylim,
             xlabel,
             ylabel,
             rot,
             fontsize,
             colormap,
             colorbar,
             position,
             table,
             yerr,
             xerr,
             stacked,
             secondary_y,
             mark_right,
             include_bool,
             backend,
             ...)

Parámetros
data: Serie o DataFrame
      El objeto para el cual se llama al método.

x:  etiqueta o posición, predeterminado None
    Solo se usa si data es un DataFrame.

y:  etiqueta, posición o lista de etiquetas, posiciones, predeterminado None
    Permite trazar una columna versus otra. Solo se usa si data es un DataFrame.

kind: str
    El tipo de gráfico a producir:
      - 'line' : gráfico de líneas (predeterminado)
      - 'bar' : gráfico de barras vertical
      - 'barh' : gráfico de barras horizontal
      - 'hist' : histograma
      - 'box' : diagrama de caja
      - 'kde' : gráfico de estimación de densidad kernel
      - 'density' : lo mismo que 'kde'
      - 'area' : gráfico de área
      - 'pie' : gráfico de tarta
      - 'scatter' : gráfico de dispersión (solo DataFrame)
      - 'hexbin' : gráfico de hexbin (solo DataFrame)


ax:   objeto de ejes de matplotlib, predeterminado None
      Un ejes de la figura actual.

subplots:   bool o secuencia de iterables, predeterminado False
            Si se agrupan las columnas en subgráficos:
              - False: No se usarán subgráficos
              - True: Crear subgráficos separados para cada columna.
              - secuencia de iterables de etiquetas de columna: Crear un subgráfico para cada grupo de columnas.
                                                                Por ejemplo [('a', 'c'), ('b', 'd')] creará 2
                                                                subgráficos: uno con las columnas 'a' y 'c',
                                                                y otro con las columnas 'b' y 'd'.
                                                                Las columnas restantes que no se especifiquen 
                                                                se trazarán en subgráficos adicionales (uno por columna).

sharex:   bool, predeterminado True si ax es None, de lo contrario False.
          En caso de subplots=True, comparte el eje x y establece algunas etiquetas del eje x en invisible; por defecto True si ax es None, de lo contrario False si se pasa un ax. Tenga en cuenta que pasar tanto un ax como sharex=True alterará todas las etiquetas del eje x para todos los ejes en una figura.

sharey:   bool, predeterminado False.
          En caso de subplots=True, comparte el eje y y establece algunas etiquetas del eje y en invisible.

layout:   tuple, opcional (filas, columnas) para el diseño de subgráficos.

figsize:  una tupla (ancho, alto) en pulgadas.
          Tamaño de un objeto figura.

use_index:  bool, predeterminado True.
            Usar el índice como marcas para el eje x.

title:  str o lista.
        Título para usar en la gráfica. Si se pasa una cadena, imprima la cadena en la parte superior de la figura.
        Si se pasa una lista y subplots es True, imprima cada elemento de la lista sobre el subgráfico correspondiente.

grid:   bool, predeterminado None (estilo matlab predeterminado).
        Líneas de cuadrícula del eje.

legend: bool o {'reverse'}.
        Coloque la leyenda en los subgráficos del eje.

style:  lista o diccionario.
        El estilo de línea matplotlib por columna.

logx:   bool o 'sym', predeterminado False.
        Usar escala logarítmica o escala logarítmica simétrica en el eje x.

logy:   bool o 'sym', predeterminado False.
        Usar escala logarítmica o escala logarítmica simétrica en el eje y.

loglog:   bool o 'sym', predeterminado False.
          Usar escala logarítmica o escala logarítmica simétrica en ambos ejes x e y.

xticks:   secuencia.
          Valores para usar en los marcadores del eje x.

yticks:   secuencia.
          Valores para usar en los marcadores del eje y.

xlim:   2-tuple/list.
        Establecer los límites x de los ejes actuales.

ylim:   2-tuple/list.
        Establecer los límites y de los ejes actuales.

xlabel:   etiqueta, opcional.
          Nombre para usar en el eje x. Por defecto, utiliza el nombre del índice como xlabel,
          o el nombre de la columna x para gráficos planos.

ylabel:   etiqueta, opcional.
          Nombre para usar en el eje y. Por defecto, no mostrará ylabel, o el nombre de la columna y para gráficos planos.

rot:  flotante, predeterminado None.
      Rotación para las marcas (xticks para gráficos verticales, yticks para gráficos horizontales).

fontsize: flotante, predeterminado None.
          Tamaño de fuente para xticks y yticks.

colormap: str o objeto colormap de matplotlib, predeterminado None.
          Mapa de colores para seleccionar colores. Si es una cadena, carga el mapa de colores con ese nombre desde matplotlib.

colorbar: bool, opcional.
          Si es True, muestra la barra de color (solo relevante para gráficos 'scatter' y 'hexbin').

position: flotante.
          Especificar alineaciones relativas para el diseño de gráficos de barra. Desde 0 (izquierda/inferior) hasta 1 (derecha/superior). El valor predeterminado es 0.5 (centro).

table:  bool, Series o DataFrame, predeterminado False.
        Si es True, dibuja una tabla utilizando los datos en el DataFrame y los datos se transpondrán para cumplir con el diseño predeterminado de matplotlib. Si se pasa una Serie o DataFrame, use los datos pasados para dibujar una tabla.

yerr:   DataFrame, Series, similar a una matriz, dict y str.
        Ver :ref:`Dibujo con barras de error <visualization.errorbars>` para más detalles.

xerr:   DataFrame, Series, similar a una matriz, dict y str.
        Equivalente a yerr.

stacked:  bool, predeterminado False en gráficos de líneas y barras, y True en gráficos de área.
          Si es True, crea un gráfico apilado.

secondary_y:  bool o secuencia, predeterminado False.
              Si es una lista/tupla, qué columnas trazar en el eje y secundario.

mark_right:   bool, predeterminado True.
              Al usar un eje secondary_y, marca automáticamente las etiquetas de columna con "(right)" en la leyenda.

include_bool:   bool, predeterminado es False.
                Si es True, los valores booleanos se pueden graficar.

backend:  str, predeterminado None.
          Backend a utilizar en lugar del backend especificado en la opción plotting.backend.
          Por ejemplo, 'matplotlib'. Alternativamente, para especificar el backend de trazado para toda la sesión, establezca pd.options.plotting.backend.

```


## Importar Libreris en colab
```python
import pandas as pd
import matplotlib.pyplot as plt

from google.colab import drive

drive.mount('/content/drive')
```