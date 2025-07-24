Análisis de Datos de Ventas de Tiendas

![alt text] (https://bing.com/th/id/BCO.5e1e499b-535e-48c9-b590-5d9fe0e8f23e.png)



Este documento describe un análisis básico de datos de ventas de múltiples tiendas, utilizando las librerías pandas para la manipulación de datos y matplotlib para la visualización.

1. Importación de Datos

Python

import pandas as pd

url = "https://raw.githubusercontent.com/alura-es-cursos/challenge1-data-science-latam/refs/heads/main/base-de-datos-challenge1-latam/tienda_1%20.csv"
url2 = "https://raw.githubusercontent.com/alura-es-cursos/challenge1-data-science-latam/refs/heads/main/base-de-datos-challenge1-latam/tienda_2.csv"
url3 = "https://raw.githubusercontent.com/alura-es-cursos/challenge1-data-science-latam/refs/heads/main/base-de-datos-challenge1-latam/tienda_3.csv"
url4 = "https://raw.githubusercontent.com/alura-es-cursos/challenge1-data-science-latam/refs/heads/main/base-de-datos-challenge1-latam/tienda_4.csv"

tienda = pd.read_csv(url)
tienda2 = pd.read_csv(url2)
tienda3 = pd.read_csv(url3)
tienda4 = pd.read_csv(url4)

tienda.head()

Este primer bloque de código se encarga de cargar los conjuntos de datos de cuatro tiendas diferentes. Cada conjunto de datos se obtiene de un archivo CSV alojado en GitHub.

    Se importó la librería pandas para el manejo de DataFrames.

    Se definieron cuatro variables url (url, url2, url3, url4), cada una apuntando a la ubicación de un archivo CSV de una tienda.

    Se usó pd.read_csv() para leer cada archivo CSV y almacenarlo en DataFrames individuales (tienda, tienda2, tienda3, tienda4).

    Finalmente, tienda.head() muestra las primeras filas del DataFrame de la primera tienda, lo que permite una inspección rápida de su estructura y contenido.

2. Análisis de Facturación

Python

import pandas as pd
import matplotlib.pyplot as plt

# ... (URLs y carga de datos repetidos del bloque anterior) ...

sumaTienda = tienda['Precio'].sum()
sumaTienda2 = tienda2['Precio'].sum()
sumaTienda3 = tienda3['Precio'].sum()
sumaTienda4 = tienda4['Precio'].sum()

lista = []
lista = ['tienda 1', 'tienda 2', 'tienda 3', 'tienda 4']
ingreso = [sumaTienda, sumaTienda2, sumaTienda3, sumaTienda4]

print(f'Ingreso total de la tienda 1 es: $ {sumaTienda}')
print(f'Ingreso total de la tienda 2 es: $ {sumaTienda2}')
print(f'Ingreso total de la tienda 3 es: $ {sumaTienda3}')
print(f'Ingreso total de la tienda 4 es: $ {sumaTienda4}')

# @title Ingreso Total
from matplotlib import pyplot as plt
df_ingresos['Ingreso Total'].plot(kind='hist', bins=20, title='Ingreso Total')
plt.gca().spines[['top', 'right',]].set_visible(False)

En esta sección, el objetivo es calcular y visualizar el ingreso total por cada tienda.

    Además de pandas, se importa matplotlib.pyplot para crear gráficos.

    Para cada DataFrame de tienda, se calcula la suma de la columna 'Precio' para obtener el ingreso total de esa tienda (ej., sumaTienda = tienda['Precio'].sum()).

    Los ingresos totales se almacenan en una lista llamada ingreso, junto con los nombres de las tiendas en la lista lista.

    Se imprimen los ingresos totales de cada tienda en la consola para una lectura clara.

    Finalmente, se intenta generar un histograma del 'Ingreso Total'. Es importante notar que la variable df_ingresos no está definida en el código proporcionado, lo que podría causar un error en esta parte del script. La intención es visualizar la distribución de los ingresos si se tuviera un DataFrame adecuado.

3. Ventas por Categoría (Visualizaciones Placeholder)

Python

# @title Precio vs Costo de envío
from matplotlib import pyplot as plt
product_cost.plot(kind='scatter', x='Precio', y='Costo de envío', s=32, alpha=.8)
plt.gca().spines[['top', 'right',]].set_visible(False)

# @title Precio
from matplotlib import pyplot as plt
product_cost['Precio'].plot(kind='hist', bins=20, title='Precio')
plt.gca().spines[['top', 'right',]].set_visible(False)

Estas dos celdas muestran visualizaciones potenciales relacionadas con las ventas por categoría, aunque el código para procesar las categorías no está presente.

    El primer gráfico intenta crear un diagrama de dispersión de 'Precio' vs 'Costo de envío' utilizando un DataFrame product_cost. Esto ayudaría a entender la relación entre el precio de un producto y su costo de envío.

    El segundo gráfico muestra un histograma de 'Precio' de product_cost, lo que daría una idea de la distribución de los precios de los productos.

    Al igual que en el caso anterior, las variables product_cost no están definidas en el fragmento de código completo, lo que indica que estas visualizaciones dependen de un procesamiento de datos previo que no se incluyó.

4. Calificación Promedio de la Tienda (Visualización Placeholder)

Python

# @title Calificación
from matplotlib import pyplot as plt
average_rating['Calificación'].plot(kind='hist', bins=20, title='Calificación')
plt.gca().spines[['top', 'right',]].set_visible(False)

Este bloque está diseñado para visualizar la distribución de las calificaciones.

    Se intenta generar un histograma de la columna 'Calificación' de un DataFrame llamado average_rating. Este gráfico sería útil para ver la frecuencia de diferentes calificaciones dentro de la base de datos.

    Similar a los casos anteriores, average_rating no está definida en el código proporcionado, por lo que su ejecución requeriría código adicional para calcular las calificaciones promedio.

5. Productos Más y Menos Vendidos (Visualización Placeholder)

Python

# @title Cantidad Vendida
from matplotlib import pyplot as plt
most_sold_products['Cantidad Vendida'].plot(kind='hist', bins=20, title='Cantidad Vendida')
plt.gca().spines[['top', 'right',]].set_visible(False)

Esta sección busca visualizar la cantidad de productos vendidos.

    El código intenta crear un histograma de la columna 'Cantidad Vendida' a partir de un DataFrame most_sold_products. Este gráfico sería útil para entender la distribución de las ventas de productos individuales.

    De nuevo, la variable most_sold_products no está definida, lo que sugiere que se necesita un paso previo para identificar y procesar los productos más y menos vendidos.

6. Envío Promedio por Tienda

Python

average_shipping_cost = all_stores.groupby('store')['Costo de envío'].mean().reset_index()

display(average_shipping_cost)

# @title Costo de envío
from matplotlib import pyplot as plt
average_shipping_cost['Costo de envío'].plot(kind='hist', bins=20, title='Costo de envío')
plt.gca().spines[['top', 'right',]].set_visible(False)

Esta última sección se enfoca en calcular y visualizar el costo de envío promedio por tienda.

    Se utiliza groupby('store') en un DataFrame all_stores para agrupar los datos por tienda. Luego, se calcula el promedio de la columna 'Costo de envío' para cada tienda y el resultado se almacena en average_shipping_cost.

    display(average_shipping_cost) mostrará este DataFrame con los costos de envío promedio.

    Finalmente, se genera un histograma del 'Costo de envío' a partir del DataFrame average_shipping_cost, lo que permite ver la distribución de los costos de envío promedio entre las tiendas.

    Es importante destacar que la variable all_stores no está definida en el código que me proporcionaste. Para que este bloque funcione, sería necesario combinar los DataFrames individuales de cada tienda (tienda, tienda2, etc.) en un solo DataFrame llamado all_stores.

En resumen, este código sienta las bases para un análisis de ventas de múltiples tiendas, centrándose en la facturación, los costos de envío y algunas visualizaciones clave. Ten en cuenta que algunas variables y pasos de pre-procesamiento no están explícitamente definidos en el fragmento proporcionado.