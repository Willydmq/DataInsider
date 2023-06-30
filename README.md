#1. Configuración del Ambiente

Para desarrollar este desafío te recomendamos trabajar directamente desde la plataforma **Google Colab**. (Recuerda que debes tener una cuenta en gmail, si aún no la tienes, debes crearla).

- Accede a la siguiente URL: [Google Colaboratory](http://colab.research.google.com/)
- Debes crear un nuevo Notebook, y asignarle el nombre que desees: Ej. `Desafio Data Insider`
- Tras seguir los pasos anteriores, debes conectar tu notebook con tu cuenta de **Google Drive**. Para ello, en una nueva celda de código digita y ejecuta:

```
from google.colab import drive
drive.mount('/content/drive')
```

```python
from google.colab import drive
drive.mount('/content/drive')
```

    Mounted at /content/drive

- Accede a las siguientes URLs para descargar los datasets que estaremos utilizando:

1.  [Forbes Global 2000 2008-2022 (mil $ unit)](https://data.world/aroissues/forbes-global-2000-2008-2019)
2.  [Fortune Global 500](https://caelum-online-public.s3.amazonaws.com/challenge_data_insider/fortune_global_500.zip)
3.  [Continentes y países](https://caelum-online-public.s3.amazonaws.com/challenge_data_insider/continentes_y_paises.zip)

- Después de descargar los datasets, crea un directorio en tu cuenta de Drive y haz el upload de todos ellos.
- Ya estás listo para avanzar a la siguiente etapa. ¡Te deseo muchos Éxitos!

```python
import pandas as pd

# Leer el archivo CSV desde tu unidad de Google Drive y almacenarlo en un DataFrame
ano_2000_2008 = pd.read_csv('/content/drive/MyDrive/BootCamp/CHALLENGE/Spring_2/aroissues-forbes-global-2000-2008-2019/data/forbes_global_2000_2008_unified_industry.csv')
ano_2000_2009 = pd.read_csv('/content/drive/MyDrive/BootCamp/CHALLENGE/Spring_2/aroissues-forbes-global-2000-2008-2019/data/forbes_global_2000_2009_unified_industry.csv')
ano_2000_2010 = pd.read_csv('/content/drive/MyDrive/BootCamp/CHALLENGE/Spring_2/aroissues-forbes-global-2000-2008-2019/data/forbes_global_2000_2010_unified_industry.csv')
ano_2000_2011 = pd.read_csv('/content/drive/MyDrive/BootCamp/CHALLENGE/Spring_2/aroissues-forbes-global-2000-2008-2019/data/forbes_global_2000_2011_unified_industry.csv')
ano_2000_2012 = pd.read_csv('/content/drive/MyDrive/BootCamp/CHALLENGE/Spring_2/aroissues-forbes-global-2000-2008-2019/data/forbes_global_2000_2012_unified_industry.csv')
ano_2000_2013 = pd.read_csv('/content/drive/MyDrive/BootCamp/CHALLENGE/Spring_2/aroissues-forbes-global-2000-2008-2019/data/forbes_global_2000_2013_unified_industry.csv')
ano_2000_2014 = pd.read_csv('/content/drive/MyDrive/BootCamp/CHALLENGE/Spring_2/aroissues-forbes-global-2000-2008-2019/data/forbes_global_2000_2014_unified_industry.csv')
ano_2000_2015 = pd.read_csv('/content/drive/MyDrive/BootCamp/CHALLENGE/Spring_2/aroissues-forbes-global-2000-2008-2019/data/forbes_global_2000_2015_unified_industry.csv')
ano_2000_2016 = pd.read_csv('/content/drive/MyDrive/BootCamp/CHALLENGE/Spring_2/aroissues-forbes-global-2000-2008-2019/data/forbes_global_2000_2016_unified_industry.csv')
ano_2000_2017 = pd.read_csv('/content/drive/MyDrive/BootCamp/CHALLENGE/Spring_2/aroissues-forbes-global-2000-2008-2019/data/forbes_global_2000_2017_unified_industry.csv')
ano_2000_2018 = pd.read_csv('/content/drive/MyDrive/BootCamp/CHALLENGE/Spring_2/aroissues-forbes-global-2000-2008-2019/data/forbes_global_2000_2018_unified_industry.csv')
ano_2000_2019 = pd.read_csv('/content/drive/MyDrive/BootCamp/CHALLENGE/Spring_2/aroissues-forbes-global-2000-2008-2019/data/forbes_global_2000_2019_unified_industry.csv')
ano_2000_2020 = pd.read_csv('/content/drive/MyDrive/BootCamp/CHALLENGE/Spring_2/aroissues-forbes-global-2000-2008-2019/data/forbes_global_2000_2020_unified_industry.csv')
ano_2000_2021 = pd.read_csv('/content/drive/MyDrive/BootCamp/CHALLENGE/Spring_2/aroissues-forbes-global-2000-2008-2019/data/forbes_global_2000_2021_unified_industry.csv')
ano_2000_2022 = pd.read_csv('/content/drive/MyDrive/BootCamp/CHALLENGE/Spring_2/aroissues-forbes-global-2000-2008-2019/data/forbes_global_2000_2022_unified_industry.csv')
```

```python
# import os

# # Obtener la lista de archivos HTML en la carpeta
# ruta_carpeta = '/content/drive/MyDrive/BootCamp/CHALLENGE/Spring_2/fortune_global_500'
# archivos_html = [f for f in os.listdir(ruta_carpeta) if f.endswith('.html')]
```

```python
# import pandas as pd

# # Recorrer la lista de archivos HTML y convertirlos a CSV
# for archivo_html in archivos_html:
#     # Leer el archivo HTML y convertirlo en un dataframe de pandas
#     ruta_archivo_html = f'{ruta_carpeta}/{archivo_html}'
#     df = pd.read_html(ruta_archivo_html)[0]

#     # Exportar el dataframe a un archivo CSV
#     ruta_archivo_csv = f'{ruta_carpeta}/{archivo_html[:-5]}.csv'
#     df.to_csv(ruta_archivo_csv, index=False)
```

```python
import pandas as pd

# Leer el archivo CSV desde tu unidad de Google Drive y almacenarlo en un DataFrame
continente = pd.read_csv('/content/drive/MyDrive/BootCamp/CHALLENGE/Spring_2/continentes_y_paises/continente.csv')
country = pd.read_csv('/content/drive/MyDrive/BootCamp/CHALLENGE/Spring_2/continentes_y_paises/country_code.csv')
```

#2. Obtención de los datos

1. Para que puedas cargar en tu notebook los archivos que almacenaste previamente en tu cuenta de Drive, debes utilizar la biblioteca [pandas](https://pandas.pydata.org/docs/user_guide/index.html).

   **_Recomendación:_** Utiliza nombres de variables que faciliten tu análisis, pues son varios los datasets que estarás consultando.

2. Adicionalmente, vas a utilizar una API para obtener datos históricos de las acciones de las empresas que entrarán en el análisis:

El enlace de la API es el siguiente: [polygon.io](https://polygon.io/)

debes seguir los pasos para obtener una API Key y también debes consultar su [documentación](https://polygon.io/docs/stocks/getting-started) para que puedas utilizarla de manera correcta.

3. Vas a obtener los datos históricos de las acciones de 5 empresas de una misma industria (Ejemplos de Industrias: Automotriz, Tecnología, Bancos, entre otras): entre el 1 de enero y el 31 de diciembre de 2022 y los vas a almacenar en 5 datasets diferentes. (Las variables que necesitas almacenar en el dataset son: El Símbolo, la Fecha, y los Precios de Apertura, Cierre, Máximo y Mínimo de las acciones)

4. Vas a exportar estos 5 datasets en formato `.csv` y los guardarás en el directorio donde están los demás datasets.

¡Ahora sí puedes avanzar a la siguiente fase! :)

```python
# import os
# from dotenv import load_dotenv
# import requests
# import pandas as pd

# # Cargar las variables de entorno desde el archivo .env
# load_dotenv('/content/drive/MyDrive/BootCamp/CHALLENGE/Spring_2/config/.env')

# # Configurar las variables de la consulta a la API
# simbolos = ['AAPL', 'GOOG', 'MSFT', 'TSLA', 'AMZN']  # Símbolos de las empresas
# fecha_inicio = '2022-01-01'  # Fecha de inicio de la consulta
# fecha_fin = '2022-12-31'  # Fecha de fin de la consulta
# api_key = os.getenv('POLYGON_API_KEY')  # API Key de Polygon.io

# # Realizar la consulta y guardar los datos en archivos CSV por separado
# for simbolo in simbolos:
#     # Realizar la consulta a la API
#     url = f'https://api.polygon.io/v2/aggs/ticker/{simbolo}/range/1/day/{fecha_inicio}/{fecha_fin}?apiKey={api_key}'
#     response = requests.get(url)

#     # Convertir la respuesta en un dataframe de pandas
#     datos = response.json()['results']
#     df = pd.DataFrame(datos)

#     # Exportar los datos a un archivo CSV
#     ruta_archivo = f'/content/drive/MyDrive/BootCamp/CHALLENGE/Spring_2/EmpresasValores/{simbolo}.csv'
#     df.to_csv(ruta_archivo, index=False)
```

#3. Data Wrangling

Data Wrangling (o "manipulación de datos") es el proceso de transformación y preparación de datos en bruto a un formato más adecuado para su análisis y toma de decisiones. Esta etapa es esencial en cualquier proyecto de análisis de datos, ya que los datos en bruto suelen estar incompletos, inconsistentes o tener formatos diferentes que necesitan ser estandarizados antes de poder ser analizados con precisión.

El Data Wrangling incluye varias tareas, como la eliminación de datos duplicados o irrelevantes, el llenado de datos faltantes, la estandarización de formatos de datos, la fusión de conjuntos de datos diferentes y la creación de variables o métricas adicionales para ayudar en el análisis. En general, el objetivo es transformar los datos en bruto en datos limpios, coherentes y listos para ser analizados mediante las técnicas de visualización de datos que estaremos desarrollando.

---

##A. En esta fase vas a explorar mejor cada uno de tus datasets de **Forbes Global 2000**, cambiar los nombres de las columnas (**Empresa, Industria, Pais, Ingresos, Ganancias, Activos y Valor de Mercado**), y crear las siguientes variables (para los datasets de Forbes 2000):

-**Margen de Rentabilidad:** Ganancias/Ingresos

-**Rentabilidad de los Activos (ROA):** Ganancias/Activos

-**Año:** Según el nombre de cada dataset

```python
import pandas as pd

ano_2000_2008 = ano_2000_2008.rename(columns={'company': 'Empresa', 'industry': 'Industria', 'country': 'Pais', 'sales': 'Ingresos',
                        'profits': 'Ganancias', 'assets': 'Activos', 'market_value': 'Valor de Mercado'})
ano_2000_2009 = ano_2000_2009.rename(columns={'company': 'Empresa', 'industry': 'Industria', 'country': 'Pais', 'sales': 'Ingresos',
                        'profits': 'Ganancias', 'assets': 'Activos', 'market_value': 'Valor de Mercado'})
ano_2000_2010 = ano_2000_2010.rename(columns={'company': 'Empresa', 'industry': 'Industria', 'country': 'Pais', 'sales': 'Ingresos',
                        'profits': 'Ganancias', 'assets': 'Activos', 'market_value': 'Valor de Mercado'})
ano_2000_2011 = ano_2000_2011.rename(columns={'company': 'Empresa', 'industry': 'Industria', 'country': 'Pais', 'sales': 'Ingresos',
                        'profits': 'Ganancias', 'assets': 'Activos', 'market_value': 'Valor de Mercado'})
ano_2000_2012 = ano_2000_2012.rename(columns={'company': 'Empresa', 'industry': 'Industria', 'country': 'Pais', 'sales': 'Ingresos',
                        'profits': 'Ganancias', 'assets': 'Activos', 'market_value': 'Valor de Mercado'})
ano_2000_2013 = ano_2000_2013.rename(columns={'company': 'Empresa', 'industry': 'Industria', 'country': 'Pais', 'sales': 'Ingresos',
                        'profits': 'Ganancias', 'assets': 'Activos', 'market_value': 'Valor de Mercado'})
ano_2000_2014 = ano_2000_2014.rename(columns={'company': 'Empresa', 'industry': 'Industria', 'country': 'Pais', 'sales': 'Ingresos',
                        'profits': 'Ganancias', 'assets': 'Activos', 'market_value': 'Valor de Mercado'})
ano_2000_2015 = ano_2000_2015.rename(columns={'company': 'Empresa', 'industry': 'Industria', 'country': 'Pais', 'sales': 'Ingresos',
                        'profits': 'Ganancias', 'assets': 'Activos', 'market_value': 'Valor de Mercado'})
ano_2000_2016 = ano_2000_2016.rename(columns={'company': 'Empresa', 'industry': 'Industria', 'country': 'Pais', 'sales': 'Ingresos',
                        'profits': 'Ganancias', 'assets': 'Activos', 'market_value': 'Valor de Mercado'})
ano_2000_2017 = ano_2000_2017.rename(columns={'company': 'Empresa', 'industry': 'Industria', 'country': 'Pais', 'sales': 'Ingresos',
                        'profits': 'Ganancias', 'assets': 'Activos', 'market_value': 'Valor de Mercado'})
ano_2000_2018 = ano_2000_2018.rename(columns={'company': 'Empresa', 'industry': 'Industria', 'country': 'Pais', 'sales': 'Ingresos',
                        'profits': 'Ganancias', 'assets': 'Activos', 'market_value': 'Valor de Mercado'})
ano_2000_2019 = ano_2000_2019.rename(columns={'company': 'Empresa', 'industry': 'Industria', 'country': 'Pais', 'sales': 'Ingresos',
                        'profits': 'Ganancias', 'assets': 'Activos', 'market_value': 'Valor de Mercado'})
ano_2000_2020 = ano_2000_2020.rename(columns={'company': 'Empresa', 'industry': 'Industria', 'country': 'Pais', 'sales': 'Ingresos',
                        'profits': 'Ganancias', 'assets': 'Activos', 'market_value': 'Valor de Mercado'})
ano_2000_2021 = ano_2000_2021.rename(columns={'company': 'Empresa', 'industry': 'Industria', 'country': 'Pais', 'sales': 'Ingresos',
                        'profits': 'Ganancias', 'assets': 'Activos', 'market_value': 'Valor de Mercado'})
ano_2000_2022 = ano_2000_2022.rename(columns={'company': 'Empresa', 'industry': 'Industria', 'country': 'Pais', 'sales': 'Ingresos',
                        'profits': 'Ganancias', 'assets': 'Activos', 'market_value': 'Valor de Mercado'})

ano_2000_2020.loc[ano_2000_2020['rank_nr'] == 402, 'Activos'] = 41000.0

# Crear las variables adicionales
ano_2000_2008['Margen de Rentabilidad'] = ano_2000_2008['Ganancias'] / ano_2000_2008['Ingresos']
ano_2000_2008['Rentabilidad de los Activos (ROA)'] = ano_2000_2008['Ganancias'] / ano_2000_2008['Activos']
ano_2000_2008['Año'] = '2008'

ano_2000_2009['Margen de Rentabilidad'] = ano_2000_2009['Ganancias'] / ano_2000_2009['Ingresos']
ano_2000_2009['Rentabilidad de los Activos (ROA)'] = ano_2000_2009['Ganancias'] / ano_2000_2009['Activos']
ano_2000_2009['Año'] = '2009'

ano_2000_2010['Margen de Rentabilidad'] = ano_2000_2010['Ganancias'] / ano_2000_2010['Ingresos']
ano_2000_2010['Rentabilidad de los Activos (ROA)'] = ano_2000_2010['Ganancias'] / ano_2000_2010['Activos']
ano_2000_2010['Año'] = '2010'

ano_2000_2011['Margen de Rentabilidad'] = ano_2000_2011['Ganancias'] / ano_2000_2011['Ingresos']
ano_2000_2011['Rentabilidad de los Activos (ROA)'] = ano_2000_2011['Ganancias'] / ano_2000_2011['Activos']
ano_2000_2011['Año'] = '2011'

ano_2000_2012['Margen de Rentabilidad'] = ano_2000_2012['Ganancias'] / ano_2000_2012['Ingresos']
ano_2000_2012['Rentabilidad de los Activos (ROA)'] = ano_2000_2012['Ganancias'] / ano_2000_2012['Activos']
ano_2000_2012['Año'] = '2012'

ano_2000_2013['Margen de Rentabilidad'] = ano_2000_2013['Ganancias'] / ano_2000_2013['Ingresos']
ano_2000_2013['Rentabilidad de los Activos (ROA)'] = ano_2000_2013['Ganancias'] / ano_2000_2013['Activos']
ano_2000_2013['Año'] = '2013'

ano_2000_2014['Margen de Rentabilidad'] = ano_2000_2014['Ganancias'] / ano_2000_2014['Ingresos']
ano_2000_2014['Rentabilidad de los Activos (ROA)'] = ano_2000_2014['Ganancias'] / ano_2000_2014['Activos']
ano_2000_2014['Año'] = '2014'

ano_2000_2015['Margen de Rentabilidad'] = ano_2000_2015['Ganancias'] / ano_2000_2015['Ingresos']
ano_2000_2015['Rentabilidad de los Activos (ROA)'] = ano_2000_2015['Ganancias'] / ano_2000_2015['Activos']
ano_2000_2015['Año'] = '2015'

ano_2000_2016['Margen de Rentabilidad'] = ano_2000_2016['Ganancias'] / ano_2000_2016['Ingresos']
ano_2000_2016['Rentabilidad de los Activos (ROA)'] = ano_2000_2016['Ganancias'] / ano_2000_2016['Activos']
ano_2000_2016['Año'] = '2016'

ano_2000_2017['Margen de Rentabilidad'] = ano_2000_2017['Ganancias'] / ano_2000_2017['Ingresos']
ano_2000_2017['Rentabilidad de los Activos (ROA)'] = ano_2000_2017['Ganancias'] / ano_2000_2017['Activos']
ano_2000_2017['Año'] = '2017'

ano_2000_2018['Margen de Rentabilidad'] = ano_2000_2018['Ganancias'] / ano_2000_2018['Ingresos']
ano_2000_2018['Rentabilidad de los Activos (ROA)'] = ano_2000_2018['Ganancias'] / ano_2000_2018['Activos']
ano_2000_2018['Año'] = '2018'

ano_2000_2019['Margen de Rentabilidad'] = ano_2000_2019['Ganancias'] / ano_2000_2019['Ingresos']
ano_2000_2019['Rentabilidad de los Activos (ROA)'] = ano_2000_2019['Ganancias'] / ano_2000_2019['Activos']
ano_2000_2019['Año'] = '2019'

ano_2000_2020['Margen de Rentabilidad'] = ano_2000_2020['Ganancias'] / ano_2000_2020['Ingresos']
ano_2000_2020['Rentabilidad de los Activos (ROA)'] = ano_2000_2020['Ganancias'] / ano_2000_2020['Activos']
ano_2000_2020['Año'] = '2020'

ano_2000_2021['Margen de Rentabilidad'] = ano_2000_2021['Ganancias'] / ano_2000_2021['Ingresos']
ano_2000_2021['Rentabilidad de los Activos (ROA)'] = ano_2000_2021['Ganancias'] / ano_2000_2021['Activos']
ano_2000_2021['Año'] = '2021'

ano_2000_2022['Margen de Rentabilidad'] = ano_2000_2022['Ganancias'] / ano_2000_2022['Ingresos']
ano_2000_2022['Rentabilidad de los Activos (ROA)'] = ano_2000_2022['Ganancias'] / ano_2000_2022['Activos']
ano_2000_2022['Año'] = '2022'

# Mostrar las primeras filas del dataframe
ano_2000_2022
```

  <div id="df-1eb2dd32-6b2b-472d-969c-de531b28adb1">
    <div class="colab-df-container">
      <div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }

</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>rank_nr</th>
      <th>Empresa</th>
      <th>Industria</th>
      <th>Pais</th>
      <th>Ingresos</th>
      <th>Ganancias</th>
      <th>Activos</th>
      <th>Valor de Mercado</th>
      <th>Margen de Rentabilidad</th>
      <th>Rentabilidad de los Activos (ROA)</th>
      <th>Año</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>Berkshire Hathaway</td>
      <td>Diversified Financials</td>
      <td>United States</td>
      <td>276094</td>
      <td>89795.0</td>
      <td>958784</td>
      <td>741476</td>
      <td>0.325233</td>
      <td>0.093655</td>
      <td>2022</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2</td>
      <td>ICBC</td>
      <td>Banking</td>
      <td>China</td>
      <td>208127</td>
      <td>54028.3</td>
      <td>5518508</td>
      <td>214425</td>
      <td>0.259593</td>
      <td>0.009790</td>
      <td>2022</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3</td>
      <td>Saudi Arabian Oil Company (Saudi Aramco)</td>
      <td>Oil &amp; Gas Operations</td>
      <td>Saudi Arabia</td>
      <td>400376</td>
      <td>105363.0</td>
      <td>576041</td>
      <td>2292077</td>
      <td>0.263160</td>
      <td>0.182909</td>
      <td>2022</td>
    </tr>
    <tr>
      <th>3</th>
      <td>4</td>
      <td>JPMorgan Chase</td>
      <td>Diversified Financials</td>
      <td>United States</td>
      <td>124542</td>
      <td>42115.0</td>
      <td>3954687</td>
      <td>374446</td>
      <td>0.338159</td>
      <td>0.010649</td>
      <td>2022</td>
    </tr>
    <tr>
      <th>4</th>
      <td>5</td>
      <td>China Construction Bank</td>
      <td>Banking</td>
      <td>China</td>
      <td>202069</td>
      <td>46887.3</td>
      <td>4746951</td>
      <td>181325</td>
      <td>0.232036</td>
      <td>0.009877</td>
      <td>2022</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>1995</th>
      <td>1995</td>
      <td>Shenzhen Feima International Supply Chain</td>
      <td>Business Services &amp; Supplies</td>
      <td>China</td>
      <td>37</td>
      <td>1408.3</td>
      <td>166</td>
      <td>1136</td>
      <td>38.062162</td>
      <td>8.483735</td>
      <td>2022</td>
    </tr>
    <tr>
      <th>1996</th>
      <td>1997</td>
      <td>NMDC</td>
      <td>Materials</td>
      <td>India</td>
      <td>3520</td>
      <td>1406.4</td>
      <td>5715</td>
      <td>6401</td>
      <td>0.399545</td>
      <td>0.246089</td>
      <td>2022</td>
    </tr>
    <tr>
      <th>1997</th>
      <td>1997</td>
      <td>Sichuan Changhong Electric</td>
      <td>Consumer Durables</td>
      <td>China</td>
      <td>15716</td>
      <td>53.1</td>
      <td>12105</td>
      <td>1957</td>
      <td>0.003379</td>
      <td>0.004387</td>
      <td>2022</td>
    </tr>
    <tr>
      <th>1998</th>
      <td>1999</td>
      <td>Satellite Chemical</td>
      <td>Chemicals</td>
      <td>China</td>
      <td>4413</td>
      <td>931.3</td>
      <td>7640</td>
      <td>9521</td>
      <td>0.211036</td>
      <td>0.121898</td>
      <td>2022</td>
    </tr>
    <tr>
      <th>1999</th>
      <td>2000</td>
      <td>Sun Communities</td>
      <td>Diversified Financials</td>
      <td>United States</td>
      <td>2273</td>
      <td>375.7</td>
      <td>13494</td>
      <td>21714</td>
      <td>0.165288</td>
      <td>0.027842</td>
      <td>2022</td>
    </tr>
  </tbody>
</table>
<p>2000 rows × 11 columns</p>
</div>
      <button class="colab-df-convert" onclick="convertToInteractive('df-1eb2dd32-6b2b-472d-969c-de531b28adb1')"
              title="Convert this dataframe to an interactive table."
              style="display:none;">

<svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
width="24px">
<path d="M0 0h24v24H0V0z" fill="none"/>
<path d="M18.56 5.44l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94zm-11 1L8.5 8.5l.94-2.06 2.06-.94-2.06-.94L8.5 2.5l-.94 2.06-2.06.94zm10 10l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94z"/><path d="M17.41 7.96l-1.37-1.37c-.4-.4-.92-.59-1.43-.59-.52 0-1.04.2-1.43.59L10.3 9.45l-7.72 7.72c-.78.78-.78 2.05 0 2.83L4 21.41c.39.39.9.59 1.41.59.51 0 1.02-.2 1.41-.59l7.78-7.78 2.81-2.81c.8-.78.8-2.07 0-2.86zM5.41 20L4 18.59l7.72-7.72 1.47 1.35L5.41 20z"/>
</svg>
</button>

  <style>
    .colab-df-container {
      display:flex;
      flex-wrap:wrap;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

      <script>
        const buttonEl =
          document.querySelector('#df-1eb2dd32-6b2b-472d-969c-de531b28adb1 button.colab-df-convert');
        buttonEl.style.display =
          google.colab.kernel.accessAllowed ? 'block' : 'none';

        async function convertToInteractive(key) {
          const element = document.querySelector('#df-1eb2dd32-6b2b-472d-969c-de531b28adb1');
          const dataTable =
            await google.colab.kernel.invokeFunction('convertToInteractive',
                                                     [key], {});
          if (!dataTable) return;

          const docLinkHtml = 'Like what you see? Visit the ' +
            '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
            + ' to learn more about interactive tables.';
          element.innerHTML = '';
          dataTable['output_type'] = 'display_data';
          await google.colab.output.renderOutput(dataTable, element);
          const docLink = document.createElement('div');
          docLink.innerHTML = docLinkHtml;
          element.appendChild(docLink);
        }
      </script>
    </div>

  </div>

##B. A los datasets de **Fortune Global 500** les vas a cambiar únicamente el nombre de las dos columnas que vas a utilizar (**Empresa, Empleados**) y añadir una nueva columna para el **Año**. De esta manera, vas a obtener datasets de Fortune con 3 columnas y 500 filas cada uno.

```python
import pandas as pd

# Cargar el dataset de Fortune Global 500
ano_500_2015 = pd.read_csv('/content/drive/MyDrive/BootCamp/CHALLENGE/Spring_2/fortune_global_500/data/fortune_global_2015.csv')
ano_500_2016 = pd.read_csv('/content/drive/MyDrive/BootCamp/CHALLENGE/Spring_2/fortune_global_500/data/fortune_global_2016.csv')
ano_500_2017 = pd.read_csv('/content/drive/MyDrive/BootCamp/CHALLENGE/Spring_2/fortune_global_500/data/fortune_global_2017.csv')
ano_500_2018 = pd.read_csv('/content/drive/MyDrive/BootCamp/CHALLENGE/Spring_2/fortune_global_500/data/fortune_global_2018.csv')
ano_500_2019 = pd.read_csv('/content/drive/MyDrive/BootCamp/CHALLENGE/Spring_2/fortune_global_500/data/fortune_global_2019.csv')
ano_500_2020 = pd.read_csv('/content/drive/MyDrive/BootCamp/CHALLENGE/Spring_2/fortune_global_500/data/fortune_global_2020.csv')
ano_500_2021 = pd.read_csv('/content/drive/MyDrive/BootCamp/CHALLENGE/Spring_2/fortune_global_500/data/fortune_global_2021.csv')
ano_500_2022 = pd.read_csv('/content/drive/MyDrive/BootCamp/CHALLENGE/Spring_2/fortune_global_500/data/fortune_global_2022.csv')

# Cambiar los nombres de las columnas
ano_500_2015 = ano_500_2015.rename(columns={'Name': 'Empresa', 'Employees': 'Empleados'})
ano_500_2016 = ano_500_2016.rename(columns={'Name': 'Empresa', 'Revenues': 'Empleados'})
ano_500_2017 = ano_500_2017.rename(columns={'Name': 'Empresa', 'Unnamed: 7': 'Empleados'})
ano_500_2018 = ano_500_2018.rename(columns={'Name': 'Empresa', 'Unnamed: 7': 'Empleados'})
ano_500_2019 = ano_500_2019.rename(columns={'Name': 'Empresa', 'Unnamed: 7': 'Empleados'})
ano_500_2020 = ano_500_2020.rename(columns={'Name': 'Empresa', 'Unnamed: 7': 'Empleados'})
ano_500_2021 = ano_500_2021.rename(columns={'Name': 'Empresa', 'Unnamed: 7': 'Empleados'})
ano_500_2022 = ano_500_2022.rename(columns={'Name': 'Empresa', 'Unnamed: 7': 'Empleados'})

# Agregar una columna para el año
ano_500_2015['Año'] = '2015'
ano_500_2016['Año'] = '2016'
ano_500_2017['Año'] = '2017'
ano_500_2018['Año'] = '2018'
ano_500_2019['Año'] = '2019'
ano_500_2020['Año'] = '2020'
ano_500_2021['Año'] = '2021'
ano_500_2022['Año'] = '2022'

# Seleccionar únicamente las columnas que necesitas
ano_500_2015 = ano_500_2015[['Empresa', 'Empleados', 'Año']]
ano_500_2016 = ano_500_2016[['Empresa', 'Empleados', 'Año']]
ano_500_2017 = ano_500_2017[['Empresa', 'Empleados', 'Año']]
ano_500_2018 = ano_500_2018[['Empresa', 'Empleados', 'Año']]
ano_500_2019 = ano_500_2019[['Empresa', 'Empleados', 'Año']]
ano_500_2020 = ano_500_2020[['Empresa', 'Empleados', 'Año']]
ano_500_2021 = ano_500_2021[['Empresa', 'Empleados', 'Año']]
ano_500_2022 = ano_500_2022[['Empresa', 'Empleados', 'Año']]
```

##C. A los datasets de **country_code y de continente** les vas a renombrar sus nombres de columna únicamente. Vas a mantener en ambos datasets las columnas del **nombre de pais y codigo** (3 letras) y en el de **continente**, vas a mantener el **nombre del continente.**

En este paso te sugerimos colocar nombres sencillos a tus columnas como: **Pais, Codigo y Continente.**

```python
import pandas as pd

# Cargar el dataset de country_code
country = pd.read_csv('/content/drive/MyDrive/BootCamp/CHALLENGE/Spring_2/continentes_y_paises/country_code.csv')

# Cambiar los nombres de las columnas
country = country.rename(columns={'Country': 'Pais', 'Code': 'Codigo'})

# Cargar el dataset de continente
continente = pd.read_csv('/content/drive/MyDrive/BootCamp/CHALLENGE/Spring_2/continentes_y_paises/continente.csv')

# Cambiar los nombres de las columnas
continente = continente.rename(columns={'Continent_Name': 'Continente', 'Three_Letter_Country_Code': 'Codigo'})
```

#4. Junción de Tablas y Análisis Exploratorio

##Parte 1

###A. Es esencial aclarar que el dataframe principal, del cual vamos a partir para desarrollar el análisis es el de `Forbes 2000 - 2022`

```python
import pandas as pd

# Crear un diccionario con las variables que deseamos combinar
dict_anos = {'ano_2000_2015': ano_2000_2015, 'ano_2000_2016': ano_2000_2016, 'ano_2000_2017': ano_2000_2017,
             'ano_2000_2018': ano_2000_2018, 'ano_2000_2019': ano_2000_2019, 'ano_2000_2020': ano_2000_2020,
             'ano_2000_2021': ano_2000_2021, 'ano_2000_2022': ano_2000_2022}

# Concatenar los dataframes del diccionario en uno solo
df_forbes_concat = pd.concat(dict_anos.values())

# Mostrar las primeras filas del dataframe resultante
df_forbes_concat
```

  <div id="df-2325922d-7a53-4dea-987b-b9ca4b021d76">
    <div class="colab-df-container">
      <div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }

</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>rank_nr</th>
      <th>Empresa</th>
      <th>Industria</th>
      <th>Pais</th>
      <th>Ingresos</th>
      <th>Ganancias</th>
      <th>Activos</th>
      <th>Valor de Mercado</th>
      <th>Margen de Rentabilidad</th>
      <th>Rentabilidad de los Activos (ROA)</th>
      <th>Año</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>ICBC</td>
      <td>Banking</td>
      <td>China</td>
      <td>166796.0</td>
      <td>44757.2</td>
      <td>3322043.0</td>
      <td>278327.0</td>
      <td>0.268335</td>
      <td>0.013473</td>
      <td>2015</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2</td>
      <td>China Construction Bank</td>
      <td>Banking</td>
      <td>China</td>
      <td>130473.0</td>
      <td>37038.9</td>
      <td>2698925.0</td>
      <td>212945.0</td>
      <td>0.283882</td>
      <td>0.013724</td>
      <td>2015</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3</td>
      <td>Agricultural Bank of China</td>
      <td>Banking</td>
      <td>China</td>
      <td>129221.0</td>
      <td>29124.5</td>
      <td>2574815.0</td>
      <td>189879.0</td>
      <td>0.225385</td>
      <td>0.011311</td>
      <td>2015</td>
    </tr>
    <tr>
      <th>3</th>
      <td>4</td>
      <td>Bank of China</td>
      <td>Banking</td>
      <td>China</td>
      <td>120297.0</td>
      <td>27526.8</td>
      <td>2458336.0</td>
      <td>199130.0</td>
      <td>0.228824</td>
      <td>0.011197</td>
      <td>2015</td>
    </tr>
    <tr>
      <th>4</th>
      <td>5</td>
      <td>Berkshire Hathaway</td>
      <td>Diversified Financials</td>
      <td>United States</td>
      <td>194673.0</td>
      <td>19872.0</td>
      <td>534618.0</td>
      <td>354813.0</td>
      <td>0.102079</td>
      <td>0.037170</td>
      <td>2015</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>1995</th>
      <td>1995</td>
      <td>Shenzhen Feima International Supply Chain</td>
      <td>Business Services &amp; Supplies</td>
      <td>China</td>
      <td>37.0</td>
      <td>1408.3</td>
      <td>166.0</td>
      <td>1136.0</td>
      <td>38.062162</td>
      <td>8.483735</td>
      <td>2022</td>
    </tr>
    <tr>
      <th>1996</th>
      <td>1997</td>
      <td>NMDC</td>
      <td>Materials</td>
      <td>India</td>
      <td>3520.0</td>
      <td>1406.4</td>
      <td>5715.0</td>
      <td>6401.0</td>
      <td>0.399545</td>
      <td>0.246089</td>
      <td>2022</td>
    </tr>
    <tr>
      <th>1997</th>
      <td>1997</td>
      <td>Sichuan Changhong Electric</td>
      <td>Consumer Durables</td>
      <td>China</td>
      <td>15716.0</td>
      <td>53.1</td>
      <td>12105.0</td>
      <td>1957.0</td>
      <td>0.003379</td>
      <td>0.004387</td>
      <td>2022</td>
    </tr>
    <tr>
      <th>1998</th>
      <td>1999</td>
      <td>Satellite Chemical</td>
      <td>Chemicals</td>
      <td>China</td>
      <td>4413.0</td>
      <td>931.3</td>
      <td>7640.0</td>
      <td>9521.0</td>
      <td>0.211036</td>
      <td>0.121898</td>
      <td>2022</td>
    </tr>
    <tr>
      <th>1999</th>
      <td>2000</td>
      <td>Sun Communities</td>
      <td>Diversified Financials</td>
      <td>United States</td>
      <td>2273.0</td>
      <td>375.7</td>
      <td>13494.0</td>
      <td>21714.0</td>
      <td>0.165288</td>
      <td>0.027842</td>
      <td>2022</td>
    </tr>
  </tbody>
</table>
<p>15998 rows × 11 columns</p>
</div>
      <button class="colab-df-convert" onclick="convertToInteractive('df-2325922d-7a53-4dea-987b-b9ca4b021d76')"
              title="Convert this dataframe to an interactive table."
              style="display:none;">

<svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
width="24px">
<path d="M0 0h24v24H0V0z" fill="none"/>
<path d="M18.56 5.44l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94zm-11 1L8.5 8.5l.94-2.06 2.06-.94-2.06-.94L8.5 2.5l-.94 2.06-2.06.94zm10 10l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94z"/><path d="M17.41 7.96l-1.37-1.37c-.4-.4-.92-.59-1.43-.59-.52 0-1.04.2-1.43.59L10.3 9.45l-7.72 7.72c-.78.78-.78 2.05 0 2.83L4 21.41c.39.39.9.59 1.41.59.51 0 1.02-.2 1.41-.59l7.78-7.78 2.81-2.81c.8-.78.8-2.07 0-2.86zM5.41 20L4 18.59l7.72-7.72 1.47 1.35L5.41 20z"/>
</svg>
</button>

  <style>
    .colab-df-container {
      display:flex;
      flex-wrap:wrap;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

      <script>
        const buttonEl =
          document.querySelector('#df-2325922d-7a53-4dea-987b-b9ca4b021d76 button.colab-df-convert');
        buttonEl.style.display =
          google.colab.kernel.accessAllowed ? 'block' : 'none';

        async function convertToInteractive(key) {
          const element = document.querySelector('#df-2325922d-7a53-4dea-987b-b9ca4b021d76');
          const dataTable =
            await google.colab.kernel.invokeFunction('convertToInteractive',
                                                     [key], {});
          if (!dataTable) return;

          const docLinkHtml = 'Like what you see? Visit the ' +
            '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
            + ' to learn more about interactive tables.';
          element.innerHTML = '';
          dataTable['output_type'] = 'display_data';
          await google.colab.output.renderOutput(dataTable, element);
          const docLink = document.createElement('div');
          docLink.innerHTML = docLinkHtml;
          element.appendChild(docLink);
        }
      </script>
    </div>

  </div>

###B. Al dataframe indicado, le vamos a añadir los dataframes de **continente y de country_code**, seleccionando únicamente las columnas de **Continente, Pais y Codigo**. Asegúrate de escoger la junción que mantiene todo el primer dataset completo.

```python
# Cargar el dataset de continente
df_country = (country )[['Pais', 'Codigo']]

# Cargar el dataset de country_code
df_continente = (continente)[['Continente', 'Codigo']]

# Unir los dataframes
df_forbes_un = df_forbes_concat
df_forbes_un = pd.merge(df_forbes_un, df_country, on='Pais', how='left')
df_forbes_un = pd.merge(df_forbes_un, df_continente, on='Codigo', how='left')

# Mostrar las primeras filas del dataframe
df_forbes_un
```

  <div id="df-86adeff8-7d57-46c5-bf2e-911aad087640">
    <div class="colab-df-container">
      <div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }

</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>rank_nr</th>
      <th>Empresa</th>
      <th>Industria</th>
      <th>Pais</th>
      <th>Ingresos</th>
      <th>Ganancias</th>
      <th>Activos</th>
      <th>Valor de Mercado</th>
      <th>Margen de Rentabilidad</th>
      <th>Rentabilidad de los Activos (ROA)</th>
      <th>Año</th>
      <th>Codigo</th>
      <th>Continente</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>ICBC</td>
      <td>Banking</td>
      <td>China</td>
      <td>166796.0</td>
      <td>44757.2</td>
      <td>3322043.0</td>
      <td>278327.0</td>
      <td>0.268335</td>
      <td>0.013473</td>
      <td>2015</td>
      <td>CHN</td>
      <td>Asia</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2</td>
      <td>China Construction Bank</td>
      <td>Banking</td>
      <td>China</td>
      <td>130473.0</td>
      <td>37038.9</td>
      <td>2698925.0</td>
      <td>212945.0</td>
      <td>0.283882</td>
      <td>0.013724</td>
      <td>2015</td>
      <td>CHN</td>
      <td>Asia</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3</td>
      <td>Agricultural Bank of China</td>
      <td>Banking</td>
      <td>China</td>
      <td>129221.0</td>
      <td>29124.5</td>
      <td>2574815.0</td>
      <td>189879.0</td>
      <td>0.225385</td>
      <td>0.011311</td>
      <td>2015</td>
      <td>CHN</td>
      <td>Asia</td>
    </tr>
    <tr>
      <th>3</th>
      <td>4</td>
      <td>Bank of China</td>
      <td>Banking</td>
      <td>China</td>
      <td>120297.0</td>
      <td>27526.8</td>
      <td>2458336.0</td>
      <td>199130.0</td>
      <td>0.228824</td>
      <td>0.011197</td>
      <td>2015</td>
      <td>CHN</td>
      <td>Asia</td>
    </tr>
    <tr>
      <th>4</th>
      <td>5</td>
      <td>Berkshire Hathaway</td>
      <td>Diversified Financials</td>
      <td>United States</td>
      <td>194673.0</td>
      <td>19872.0</td>
      <td>534618.0</td>
      <td>354813.0</td>
      <td>0.102079</td>
      <td>0.037170</td>
      <td>2015</td>
      <td>USA</td>
      <td>North America</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>16281</th>
      <td>1995</td>
      <td>Shenzhen Feima International Supply Chain</td>
      <td>Business Services &amp; Supplies</td>
      <td>China</td>
      <td>37.0</td>
      <td>1408.3</td>
      <td>166.0</td>
      <td>1136.0</td>
      <td>38.062162</td>
      <td>8.483735</td>
      <td>2022</td>
      <td>CHN</td>
      <td>Asia</td>
    </tr>
    <tr>
      <th>16282</th>
      <td>1997</td>
      <td>NMDC</td>
      <td>Materials</td>
      <td>India</td>
      <td>3520.0</td>
      <td>1406.4</td>
      <td>5715.0</td>
      <td>6401.0</td>
      <td>0.399545</td>
      <td>0.246089</td>
      <td>2022</td>
      <td>IND</td>
      <td>Asia</td>
    </tr>
    <tr>
      <th>16283</th>
      <td>1997</td>
      <td>Sichuan Changhong Electric</td>
      <td>Consumer Durables</td>
      <td>China</td>
      <td>15716.0</td>
      <td>53.1</td>
      <td>12105.0</td>
      <td>1957.0</td>
      <td>0.003379</td>
      <td>0.004387</td>
      <td>2022</td>
      <td>CHN</td>
      <td>Asia</td>
    </tr>
    <tr>
      <th>16284</th>
      <td>1999</td>
      <td>Satellite Chemical</td>
      <td>Chemicals</td>
      <td>China</td>
      <td>4413.0</td>
      <td>931.3</td>
      <td>7640.0</td>
      <td>9521.0</td>
      <td>0.211036</td>
      <td>0.121898</td>
      <td>2022</td>
      <td>CHN</td>
      <td>Asia</td>
    </tr>
    <tr>
      <th>16285</th>
      <td>2000</td>
      <td>Sun Communities</td>
      <td>Diversified Financials</td>
      <td>United States</td>
      <td>2273.0</td>
      <td>375.7</td>
      <td>13494.0</td>
      <td>21714.0</td>
      <td>0.165288</td>
      <td>0.027842</td>
      <td>2022</td>
      <td>USA</td>
      <td>North America</td>
    </tr>
  </tbody>
</table>
<p>16286 rows × 13 columns</p>
</div>
      <button class="colab-df-convert" onclick="convertToInteractive('df-86adeff8-7d57-46c5-bf2e-911aad087640')"
              title="Convert this dataframe to an interactive table."
              style="display:none;">

<svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
width="24px">
<path d="M0 0h24v24H0V0z" fill="none"/>
<path d="M18.56 5.44l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94zm-11 1L8.5 8.5l.94-2.06 2.06-.94-2.06-.94L8.5 2.5l-.94 2.06-2.06.94zm10 10l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94z"/><path d="M17.41 7.96l-1.37-1.37c-.4-.4-.92-.59-1.43-.59-.52 0-1.04.2-1.43.59L10.3 9.45l-7.72 7.72c-.78.78-.78 2.05 0 2.83L4 21.41c.39.39.9.59 1.41.59.51 0 1.02-.2 1.41-.59l7.78-7.78 2.81-2.81c.8-.78.8-2.07 0-2.86zM5.41 20L4 18.59l7.72-7.72 1.47 1.35L5.41 20z"/>
</svg>
</button>

  <style>
    .colab-df-container {
      display:flex;
      flex-wrap:wrap;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

      <script>
        const buttonEl =
          document.querySelector('#df-86adeff8-7d57-46c5-bf2e-911aad087640 button.colab-df-convert');
        buttonEl.style.display =
          google.colab.kernel.accessAllowed ? 'block' : 'none';

        async function convertToInteractive(key) {
          const element = document.querySelector('#df-86adeff8-7d57-46c5-bf2e-911aad087640');
          const dataTable =
            await google.colab.kernel.invokeFunction('convertToInteractive',
                                                     [key], {});
          if (!dataTable) return;

          const docLinkHtml = 'Like what you see? Visit the ' +
            '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
            + ' to learn more about interactive tables.';
          element.innerHTML = '';
          dataTable['output_type'] = 'display_data';
          await google.colab.output.renderOutput(dataTable, element);
          const docLink = document.createElement('div');
          docLink.innerHTML = docLinkHtml;
          element.appendChild(docLink);
        }
      </script>
    </div>

  </div>

###C. Vas a identificar en que columnas tienes valores faltantes, localizar los registros o las filas con los datos faltantes y tomar una acción de acuerdo con lo que veas (Ejemplo: El nombre del país está escrito de forma incorrecta, hay inconsistencias en la fila, etc).

Observación: En la medida de lo posible, debes tratar de preservar todos los datos contenidos en tu dataset antes de ir a eliminar alguna fila.

```python
# Identificar los valores faltantes
##print(df_forbes_un.isna().sum())

# Tomar acciones para tratar los valores faltantes
# Por ejemplo, rellenar los valores faltantes de la columna Codigo con 'N/A'
##df_forbes['Codigo'] = df_forbes['Codigo'].fillna('N/A')

# Mostrar las primeras filas del dataframe
print(df_forbes_un.isna().sum())
df_forbes_un
```

    rank_nr                                0
    Empresa                                0
    Industria                              0
    Pais                                   0
    Ingresos                               8
    Ganancias                              2
    Activos                               15
    Valor de Mercado                       6
    Margen de Rentabilidad                10
    Rentabilidad de los Activos (ROA)     16
    Año                                    0
    Codigo                               513
    Continente                           513
    dtype: int64

  <div id="df-545d1ea8-1335-4ba1-ab28-ad458af2d9c1">
    <div class="colab-df-container">
      <div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }

</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>rank_nr</th>
      <th>Empresa</th>
      <th>Industria</th>
      <th>Pais</th>
      <th>Ingresos</th>
      <th>Ganancias</th>
      <th>Activos</th>
      <th>Valor de Mercado</th>
      <th>Margen de Rentabilidad</th>
      <th>Rentabilidad de los Activos (ROA)</th>
      <th>Año</th>
      <th>Codigo</th>
      <th>Continente</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>ICBC</td>
      <td>Banking</td>
      <td>China</td>
      <td>166796.0</td>
      <td>44757.2</td>
      <td>3322043.0</td>
      <td>278327.0</td>
      <td>0.268335</td>
      <td>0.013473</td>
      <td>2015</td>
      <td>CHN</td>
      <td>Asia</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2</td>
      <td>China Construction Bank</td>
      <td>Banking</td>
      <td>China</td>
      <td>130473.0</td>
      <td>37038.9</td>
      <td>2698925.0</td>
      <td>212945.0</td>
      <td>0.283882</td>
      <td>0.013724</td>
      <td>2015</td>
      <td>CHN</td>
      <td>Asia</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3</td>
      <td>Agricultural Bank of China</td>
      <td>Banking</td>
      <td>China</td>
      <td>129221.0</td>
      <td>29124.5</td>
      <td>2574815.0</td>
      <td>189879.0</td>
      <td>0.225385</td>
      <td>0.011311</td>
      <td>2015</td>
      <td>CHN</td>
      <td>Asia</td>
    </tr>
    <tr>
      <th>3</th>
      <td>4</td>
      <td>Bank of China</td>
      <td>Banking</td>
      <td>China</td>
      <td>120297.0</td>
      <td>27526.8</td>
      <td>2458336.0</td>
      <td>199130.0</td>
      <td>0.228824</td>
      <td>0.011197</td>
      <td>2015</td>
      <td>CHN</td>
      <td>Asia</td>
    </tr>
    <tr>
      <th>4</th>
      <td>5</td>
      <td>Berkshire Hathaway</td>
      <td>Diversified Financials</td>
      <td>United States</td>
      <td>194673.0</td>
      <td>19872.0</td>
      <td>534618.0</td>
      <td>354813.0</td>
      <td>0.102079</td>
      <td>0.037170</td>
      <td>2015</td>
      <td>USA</td>
      <td>North America</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>16281</th>
      <td>1995</td>
      <td>Shenzhen Feima International Supply Chain</td>
      <td>Business Services &amp; Supplies</td>
      <td>China</td>
      <td>37.0</td>
      <td>1408.3</td>
      <td>166.0</td>
      <td>1136.0</td>
      <td>38.062162</td>
      <td>8.483735</td>
      <td>2022</td>
      <td>CHN</td>
      <td>Asia</td>
    </tr>
    <tr>
      <th>16282</th>
      <td>1997</td>
      <td>NMDC</td>
      <td>Materials</td>
      <td>India</td>
      <td>3520.0</td>
      <td>1406.4</td>
      <td>5715.0</td>
      <td>6401.0</td>
      <td>0.399545</td>
      <td>0.246089</td>
      <td>2022</td>
      <td>IND</td>
      <td>Asia</td>
    </tr>
    <tr>
      <th>16283</th>
      <td>1997</td>
      <td>Sichuan Changhong Electric</td>
      <td>Consumer Durables</td>
      <td>China</td>
      <td>15716.0</td>
      <td>53.1</td>
      <td>12105.0</td>
      <td>1957.0</td>
      <td>0.003379</td>
      <td>0.004387</td>
      <td>2022</td>
      <td>CHN</td>
      <td>Asia</td>
    </tr>
    <tr>
      <th>16284</th>
      <td>1999</td>
      <td>Satellite Chemical</td>
      <td>Chemicals</td>
      <td>China</td>
      <td>4413.0</td>
      <td>931.3</td>
      <td>7640.0</td>
      <td>9521.0</td>
      <td>0.211036</td>
      <td>0.121898</td>
      <td>2022</td>
      <td>CHN</td>
      <td>Asia</td>
    </tr>
    <tr>
      <th>16285</th>
      <td>2000</td>
      <td>Sun Communities</td>
      <td>Diversified Financials</td>
      <td>United States</td>
      <td>2273.0</td>
      <td>375.7</td>
      <td>13494.0</td>
      <td>21714.0</td>
      <td>0.165288</td>
      <td>0.027842</td>
      <td>2022</td>
      <td>USA</td>
      <td>North America</td>
    </tr>
  </tbody>
</table>
<p>16286 rows × 13 columns</p>
</div>
      <button class="colab-df-convert" onclick="convertToInteractive('df-545d1ea8-1335-4ba1-ab28-ad458af2d9c1')"
              title="Convert this dataframe to an interactive table."
              style="display:none;">

<svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
width="24px">
<path d="M0 0h24v24H0V0z" fill="none"/>
<path d="M18.56 5.44l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94zm-11 1L8.5 8.5l.94-2.06 2.06-.94-2.06-.94L8.5 2.5l-.94 2.06-2.06.94zm10 10l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94z"/><path d="M17.41 7.96l-1.37-1.37c-.4-.4-.92-.59-1.43-.59-.52 0-1.04.2-1.43.59L10.3 9.45l-7.72 7.72c-.78.78-.78 2.05 0 2.83L4 21.41c.39.39.9.59 1.41.59.51 0 1.02-.2 1.41-.59l7.78-7.78 2.81-2.81c.8-.78.8-2.07 0-2.86zM5.41 20L4 18.59l7.72-7.72 1.47 1.35L5.41 20z"/>
</svg>
</button>

  <style>
    .colab-df-container {
      display:flex;
      flex-wrap:wrap;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

      <script>
        const buttonEl =
          document.querySelector('#df-545d1ea8-1335-4ba1-ab28-ad458af2d9c1 button.colab-df-convert');
        buttonEl.style.display =
          google.colab.kernel.accessAllowed ? 'block' : 'none';

        async function convertToInteractive(key) {
          const element = document.querySelector('#df-545d1ea8-1335-4ba1-ab28-ad458af2d9c1');
          const dataTable =
            await google.colab.kernel.invokeFunction('convertToInteractive',
                                                     [key], {});
          if (!dataTable) return;

          const docLinkHtml = 'Like what you see? Visit the ' +
            '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
            + ' to learn more about interactive tables.';
          element.innerHTML = '';
          dataTable['output_type'] = 'display_data';
          await google.colab.output.renderOutput(dataTable, element);
          const docLink = document.createElement('div');
          docLink.innerHTML = docLinkHtml;
          element.appendChild(docLink);
        }
      </script>
    </div>

  </div>

```python
import pandas as pd

# Mostrar las filas con valores nulos en la columna 'Codigo'
df_vacias = df_forbes_un[df_forbes_un['Codigo'].isnull()]
df_vacias
```

  <div id="df-cbb8056c-48eb-4aac-b411-5ac197939231">
    <div class="colab-df-container">
      <div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }

</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>rank_nr</th>
      <th>Empresa</th>
      <th>Industria</th>
      <th>Pais</th>
      <th>Ingresos</th>
      <th>Ganancias</th>
      <th>Activos</th>
      <th>Valor de Mercado</th>
      <th>Margen de Rentabilidad</th>
      <th>Rentabilidad de los Activos (ROA)</th>
      <th>Año</th>
      <th>Codigo</th>
      <th>Continente</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>17</th>
      <td>18</td>
      <td>Samsung Electronics</td>
      <td>Semiconductors</td>
      <td>South Korea</td>
      <td>195891.0</td>
      <td>21927.8</td>
      <td>209637.0</td>
      <td>199356.0</td>
      <td>0.111939</td>
      <td>0.104599</td>
      <td>2015</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>119</th>
      <td>117</td>
      <td>Hyundai Motor</td>
      <td>Consumer Durables</td>
      <td>South Korea</td>
      <td>84791.0</td>
      <td>6979.3</td>
      <td>133945.0</td>
      <td>32854.0</td>
      <td>0.082312</td>
      <td>0.052106</td>
      <td>2015</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>174</th>
      <td>171</td>
      <td>Korea Electric Power</td>
      <td>Utilities</td>
      <td>South Korea</td>
      <td>54600.0</td>
      <td>2552.5</td>
      <td>148941.0</td>
      <td>27040.0</td>
      <td>0.046749</td>
      <td>0.017138</td>
      <td>2015</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>283</th>
      <td>279</td>
      <td>Shinhan Financial Group</td>
      <td>Diversified Financials</td>
      <td>South Korea</td>
      <td>20072.0</td>
      <td>1948.6</td>
      <td>307530.0</td>
      <td>17791.0</td>
      <td>0.097081</td>
      <td>0.006336</td>
      <td>2015</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>302</th>
      <td>298</td>
      <td>Hyundai Mobis</td>
      <td>Consumer Durables</td>
      <td>South Korea</td>
      <td>34375.0</td>
      <td>3251.2</td>
      <td>35584.0</td>
      <td>21106.0</td>
      <td>0.094580</td>
      <td>0.091367</td>
      <td>2015</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>16082</th>
      <td>1798</td>
      <td>Korea Zinc</td>
      <td>Materials</td>
      <td>South Korea</td>
      <td>8712.0</td>
      <td>704.5</td>
      <td>8382.0</td>
      <td>8857.0</td>
      <td>0.080865</td>
      <td>0.084049</td>
      <td>2022</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>16136</th>
      <td>1850</td>
      <td>Korean Air</td>
      <td>Transportation</td>
      <td>South Korea</td>
      <td>7873.0</td>
      <td>489.8</td>
      <td>22437.0</td>
      <td>8813.0</td>
      <td>0.062213</td>
      <td>0.021830</td>
      <td>2022</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>16176</th>
      <td>1891</td>
      <td>F&amp;F</td>
      <td>Consumer Durables</td>
      <td>South Korea</td>
      <td>635.0</td>
      <td>1661.6</td>
      <td>2450.0</td>
      <td>892.0</td>
      <td>2.616693</td>
      <td>0.678204</td>
      <td>2022</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>16181</th>
      <td>1893</td>
      <td>Samsung SDS</td>
      <td>IT Software &amp; Services</td>
      <td>South Korea</td>
      <td>11902.0</td>
      <td>533.7</td>
      <td>8847.0</td>
      <td>8708.0</td>
      <td>0.044841</td>
      <td>0.060326</td>
      <td>2022</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>16262</th>
      <td>1976</td>
      <td>JB Financial Group</td>
      <td>Banking</td>
      <td>South Korea</td>
      <td>2002.0</td>
      <td>426.0</td>
      <td>47441.0</td>
      <td>1413.0</td>
      <td>0.212787</td>
      <td>0.008980</td>
      <td>2022</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
<p>513 rows × 13 columns</p>
</div>
      <button class="colab-df-convert" onclick="convertToInteractive('df-cbb8056c-48eb-4aac-b411-5ac197939231')"
              title="Convert this dataframe to an interactive table."
              style="display:none;">

<svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
width="24px">
<path d="M0 0h24v24H0V0z" fill="none"/>
<path d="M18.56 5.44l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94zm-11 1L8.5 8.5l.94-2.06 2.06-.94-2.06-.94L8.5 2.5l-.94 2.06-2.06.94zm10 10l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94z"/><path d="M17.41 7.96l-1.37-1.37c-.4-.4-.92-.59-1.43-.59-.52 0-1.04.2-1.43.59L10.3 9.45l-7.72 7.72c-.78.78-.78 2.05 0 2.83L4 21.41c.39.39.9.59 1.41.59.51 0 1.02-.2 1.41-.59l7.78-7.78 2.81-2.81c.8-.78.8-2.07 0-2.86zM5.41 20L4 18.59l7.72-7.72 1.47 1.35L5.41 20z"/>
</svg>
</button>

  <style>
    .colab-df-container {
      display:flex;
      flex-wrap:wrap;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

      <script>
        const buttonEl =
          document.querySelector('#df-cbb8056c-48eb-4aac-b411-5ac197939231 button.colab-df-convert');
        buttonEl.style.display =
          google.colab.kernel.accessAllowed ? 'block' : 'none';

        async function convertToInteractive(key) {
          const element = document.querySelector('#df-cbb8056c-48eb-4aac-b411-5ac197939231');
          const dataTable =
            await google.colab.kernel.invokeFunction('convertToInteractive',
                                                     [key], {});
          if (!dataTable) return;

          const docLinkHtml = 'Like what you see? Visit the ' +
            '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
            + ' to learn more about interactive tables.';
          element.innerHTML = '';
          dataTable['output_type'] = 'display_data';
          await google.colab.output.renderOutput(dataTable, element);
          const docLink = document.createElement('div');
          docLink.innerHTML = docLinkHtml;
          element.appendChild(docLink);
        }
      </script>
    </div>

  </div>

##¡Extra!

Trata de localizar los nombres de las empresas que aparecen en la lista de Fortune que no tuvieron correspondiente con la lista de Forbes. (Si los logras ubicar, realiza los respectivos ajustes a los nombres para que puedas traer la información faltante sobre el número de empleados)

```python
# Actualizar los valores para el país 'South Korea'
df_forbes_un.loc[df_forbes_un['Pais'] == 'South Korea', 'Codigo'] = 'SKS'
df_forbes_un.loc[df_forbes_un['Pais'] == 'South Korea', 'Continente'] = 'Asia'

# Mostrar las primeras filas del dataframe
df_forbes_un
```

  <div id="df-17c40180-1996-40d6-a0b5-263d8fc198ae">
    <div class="colab-df-container">
      <div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }

</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>rank_nr</th>
      <th>Empresa</th>
      <th>Industria</th>
      <th>Pais</th>
      <th>Ingresos</th>
      <th>Ganancias</th>
      <th>Activos</th>
      <th>Valor de Mercado</th>
      <th>Margen de Rentabilidad</th>
      <th>Rentabilidad de los Activos (ROA)</th>
      <th>Año</th>
      <th>Codigo</th>
      <th>Continente</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>ICBC</td>
      <td>Banking</td>
      <td>China</td>
      <td>166796.0</td>
      <td>44757.2</td>
      <td>3322043.0</td>
      <td>278327.0</td>
      <td>0.268335</td>
      <td>0.013473</td>
      <td>2015</td>
      <td>CHN</td>
      <td>Asia</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2</td>
      <td>China Construction Bank</td>
      <td>Banking</td>
      <td>China</td>
      <td>130473.0</td>
      <td>37038.9</td>
      <td>2698925.0</td>
      <td>212945.0</td>
      <td>0.283882</td>
      <td>0.013724</td>
      <td>2015</td>
      <td>CHN</td>
      <td>Asia</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3</td>
      <td>Agricultural Bank of China</td>
      <td>Banking</td>
      <td>China</td>
      <td>129221.0</td>
      <td>29124.5</td>
      <td>2574815.0</td>
      <td>189879.0</td>
      <td>0.225385</td>
      <td>0.011311</td>
      <td>2015</td>
      <td>CHN</td>
      <td>Asia</td>
    </tr>
    <tr>
      <th>3</th>
      <td>4</td>
      <td>Bank of China</td>
      <td>Banking</td>
      <td>China</td>
      <td>120297.0</td>
      <td>27526.8</td>
      <td>2458336.0</td>
      <td>199130.0</td>
      <td>0.228824</td>
      <td>0.011197</td>
      <td>2015</td>
      <td>CHN</td>
      <td>Asia</td>
    </tr>
    <tr>
      <th>4</th>
      <td>5</td>
      <td>Berkshire Hathaway</td>
      <td>Diversified Financials</td>
      <td>United States</td>
      <td>194673.0</td>
      <td>19872.0</td>
      <td>534618.0</td>
      <td>354813.0</td>
      <td>0.102079</td>
      <td>0.037170</td>
      <td>2015</td>
      <td>USA</td>
      <td>North America</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>16281</th>
      <td>1995</td>
      <td>Shenzhen Feima International Supply Chain</td>
      <td>Business Services &amp; Supplies</td>
      <td>China</td>
      <td>37.0</td>
      <td>1408.3</td>
      <td>166.0</td>
      <td>1136.0</td>
      <td>38.062162</td>
      <td>8.483735</td>
      <td>2022</td>
      <td>CHN</td>
      <td>Asia</td>
    </tr>
    <tr>
      <th>16282</th>
      <td>1997</td>
      <td>NMDC</td>
      <td>Materials</td>
      <td>India</td>
      <td>3520.0</td>
      <td>1406.4</td>
      <td>5715.0</td>
      <td>6401.0</td>
      <td>0.399545</td>
      <td>0.246089</td>
      <td>2022</td>
      <td>IND</td>
      <td>Asia</td>
    </tr>
    <tr>
      <th>16283</th>
      <td>1997</td>
      <td>Sichuan Changhong Electric</td>
      <td>Consumer Durables</td>
      <td>China</td>
      <td>15716.0</td>
      <td>53.1</td>
      <td>12105.0</td>
      <td>1957.0</td>
      <td>0.003379</td>
      <td>0.004387</td>
      <td>2022</td>
      <td>CHN</td>
      <td>Asia</td>
    </tr>
    <tr>
      <th>16284</th>
      <td>1999</td>
      <td>Satellite Chemical</td>
      <td>Chemicals</td>
      <td>China</td>
      <td>4413.0</td>
      <td>931.3</td>
      <td>7640.0</td>
      <td>9521.0</td>
      <td>0.211036</td>
      <td>0.121898</td>
      <td>2022</td>
      <td>CHN</td>
      <td>Asia</td>
    </tr>
    <tr>
      <th>16285</th>
      <td>2000</td>
      <td>Sun Communities</td>
      <td>Diversified Financials</td>
      <td>United States</td>
      <td>2273.0</td>
      <td>375.7</td>
      <td>13494.0</td>
      <td>21714.0</td>
      <td>0.165288</td>
      <td>0.027842</td>
      <td>2022</td>
      <td>USA</td>
      <td>North America</td>
    </tr>
  </tbody>
</table>
<p>16286 rows × 13 columns</p>
</div>
      <button class="colab-df-convert" onclick="convertToInteractive('df-17c40180-1996-40d6-a0b5-263d8fc198ae')"
              title="Convert this dataframe to an interactive table."
              style="display:none;">

<svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
width="24px">
<path d="M0 0h24v24H0V0z" fill="none"/>
<path d="M18.56 5.44l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94zm-11 1L8.5 8.5l.94-2.06 2.06-.94-2.06-.94L8.5 2.5l-.94 2.06-2.06.94zm10 10l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94z"/><path d="M17.41 7.96l-1.37-1.37c-.4-.4-.92-.59-1.43-.59-.52 0-1.04.2-1.43.59L10.3 9.45l-7.72 7.72c-.78.78-.78 2.05 0 2.83L4 21.41c.39.39.9.59 1.41.59.51 0 1.02-.2 1.41-.59l7.78-7.78 2.81-2.81c.8-.78.8-2.07 0-2.86zM5.41 20L4 18.59l7.72-7.72 1.47 1.35L5.41 20z"/>
</svg>
</button>

  <style>
    .colab-df-container {
      display:flex;
      flex-wrap:wrap;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

      <script>
        const buttonEl =
          document.querySelector('#df-17c40180-1996-40d6-a0b5-263d8fc198ae button.colab-df-convert');
        buttonEl.style.display =
          google.colab.kernel.accessAllowed ? 'block' : 'none';

        async function convertToInteractive(key) {
          const element = document.querySelector('#df-17c40180-1996-40d6-a0b5-263d8fc198ae');
          const dataTable =
            await google.colab.kernel.invokeFunction('convertToInteractive',
                                                     [key], {});
          if (!dataTable) return;

          const docLinkHtml = 'Like what you see? Visit the ' +
            '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
            + ' to learn more about interactive tables.';
          element.innerHTML = '';
          dataTable['output_type'] = 'display_data';
          await google.colab.output.renderOutput(dataTable, element);
          const docLink = document.createElement('div');
          docLink.innerHTML = docLinkHtml;
          element.appendChild(docLink);
        }
      </script>
    </div>

  </div>

```python
import pandas as pd

# Mostrar las filas con valores nulos en la columna 'Codigo'
df_vacias = df_forbes_un[df_forbes_un['Codigo'].isnull()]
df_vacias
```

  <div id="df-af57cab6-3717-4644-af46-ed43f8123fa2">
    <div class="colab-df-container">
      <div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }

</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>rank_nr</th>
      <th>Empresa</th>
      <th>Industria</th>
      <th>Pais</th>
      <th>Ingresos</th>
      <th>Ganancias</th>
      <th>Activos</th>
      <th>Valor de Mercado</th>
      <th>Margen de Rentabilidad</th>
      <th>Rentabilidad de los Activos (ROA)</th>
      <th>Año</th>
      <th>Codigo</th>
      <th>Continente</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>13711</th>
      <td>True</td>
      <td>fred/companies/F2K/2021/105837</td>
      <td>IT Software &amp; Services</td>
      <td>5855</td>
      <td>68126.0</td>
      <td>1793.0</td>
      <td>NaN</td>
      <td>235.0</td>
      <td>0.026319</td>
      <td>NaN</td>
      <td>2021</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>14997</th>
      <td>True</td>
      <td>fred/companies/F2K/2022/105837</td>
      <td>IT Software &amp; Services</td>
      <td>21274</td>
      <td>28636.0</td>
      <td>370.0</td>
      <td>1468.0</td>
      <td>632.0</td>
      <td>0.012921</td>
      <td>0.252044</td>
      <td>2022</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
</div>
      <button class="colab-df-convert" onclick="convertToInteractive('df-af57cab6-3717-4644-af46-ed43f8123fa2')"
              title="Convert this dataframe to an interactive table."
              style="display:none;">

<svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
width="24px">
<path d="M0 0h24v24H0V0z" fill="none"/>
<path d="M18.56 5.44l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94zm-11 1L8.5 8.5l.94-2.06 2.06-.94-2.06-.94L8.5 2.5l-.94 2.06-2.06.94zm10 10l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94z"/><path d="M17.41 7.96l-1.37-1.37c-.4-.4-.92-.59-1.43-.59-.52 0-1.04.2-1.43.59L10.3 9.45l-7.72 7.72c-.78.78-.78 2.05 0 2.83L4 21.41c.39.39.9.59 1.41.59.51 0 1.02-.2 1.41-.59l7.78-7.78 2.81-2.81c.8-.78.8-2.07 0-2.86zM5.41 20L4 18.59l7.72-7.72 1.47 1.35L5.41 20z"/>
</svg>
</button>

  <style>
    .colab-df-container {
      display:flex;
      flex-wrap:wrap;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

      <script>
        const buttonEl =
          document.querySelector('#df-af57cab6-3717-4644-af46-ed43f8123fa2 button.colab-df-convert');
        buttonEl.style.display =
          google.colab.kernel.accessAllowed ? 'block' : 'none';

        async function convertToInteractive(key) {
          const element = document.querySelector('#df-af57cab6-3717-4644-af46-ed43f8123fa2');
          const dataTable =
            await google.colab.kernel.invokeFunction('convertToInteractive',
                                                     [key], {});
          if (!dataTable) return;

          const docLinkHtml = 'Like what you see? Visit the ' +
            '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
            + ' to learn more about interactive tables.';
          element.innerHTML = '';
          dataTable['output_type'] = 'display_data';
          await google.colab.output.renderOutput(dataTable, element);
          const docLink = document.createElement('div');
          docLink.innerHTML = docLinkHtml;
          element.appendChild(docLink);
        }
      </script>
    </div>

  </div>

```python
import pandas as pd

# Eliminar las filas con valores nulos en la columna 'Codigo'
df_forbes_un = df_forbes_un.dropna(subset=['Codigo'])

# Mostrar las primeras filas del dataframe resultante
df_forbes_un
```

  <div id="df-fc9b81fa-b53f-4837-8916-845ce7782d26">
    <div class="colab-df-container">
      <div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }

</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>rank_nr</th>
      <th>Empresa</th>
      <th>Industria</th>
      <th>Pais</th>
      <th>Ingresos</th>
      <th>Ganancias</th>
      <th>Activos</th>
      <th>Valor de Mercado</th>
      <th>Margen de Rentabilidad</th>
      <th>Rentabilidad de los Activos (ROA)</th>
      <th>Año</th>
      <th>Codigo</th>
      <th>Continente</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>ICBC</td>
      <td>Banking</td>
      <td>China</td>
      <td>166796.0</td>
      <td>44757.2</td>
      <td>3322043.0</td>
      <td>278327.0</td>
      <td>0.268335</td>
      <td>0.013473</td>
      <td>2015</td>
      <td>CHN</td>
      <td>Asia</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2</td>
      <td>China Construction Bank</td>
      <td>Banking</td>
      <td>China</td>
      <td>130473.0</td>
      <td>37038.9</td>
      <td>2698925.0</td>
      <td>212945.0</td>
      <td>0.283882</td>
      <td>0.013724</td>
      <td>2015</td>
      <td>CHN</td>
      <td>Asia</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3</td>
      <td>Agricultural Bank of China</td>
      <td>Banking</td>
      <td>China</td>
      <td>129221.0</td>
      <td>29124.5</td>
      <td>2574815.0</td>
      <td>189879.0</td>
      <td>0.225385</td>
      <td>0.011311</td>
      <td>2015</td>
      <td>CHN</td>
      <td>Asia</td>
    </tr>
    <tr>
      <th>3</th>
      <td>4</td>
      <td>Bank of China</td>
      <td>Banking</td>
      <td>China</td>
      <td>120297.0</td>
      <td>27526.8</td>
      <td>2458336.0</td>
      <td>199130.0</td>
      <td>0.228824</td>
      <td>0.011197</td>
      <td>2015</td>
      <td>CHN</td>
      <td>Asia</td>
    </tr>
    <tr>
      <th>4</th>
      <td>5</td>
      <td>Berkshire Hathaway</td>
      <td>Diversified Financials</td>
      <td>United States</td>
      <td>194673.0</td>
      <td>19872.0</td>
      <td>534618.0</td>
      <td>354813.0</td>
      <td>0.102079</td>
      <td>0.037170</td>
      <td>2015</td>
      <td>USA</td>
      <td>North America</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>16281</th>
      <td>1995</td>
      <td>Shenzhen Feima International Supply Chain</td>
      <td>Business Services &amp; Supplies</td>
      <td>China</td>
      <td>37.0</td>
      <td>1408.3</td>
      <td>166.0</td>
      <td>1136.0</td>
      <td>38.062162</td>
      <td>8.483735</td>
      <td>2022</td>
      <td>CHN</td>
      <td>Asia</td>
    </tr>
    <tr>
      <th>16282</th>
      <td>1997</td>
      <td>NMDC</td>
      <td>Materials</td>
      <td>India</td>
      <td>3520.0</td>
      <td>1406.4</td>
      <td>5715.0</td>
      <td>6401.0</td>
      <td>0.399545</td>
      <td>0.246089</td>
      <td>2022</td>
      <td>IND</td>
      <td>Asia</td>
    </tr>
    <tr>
      <th>16283</th>
      <td>1997</td>
      <td>Sichuan Changhong Electric</td>
      <td>Consumer Durables</td>
      <td>China</td>
      <td>15716.0</td>
      <td>53.1</td>
      <td>12105.0</td>
      <td>1957.0</td>
      <td>0.003379</td>
      <td>0.004387</td>
      <td>2022</td>
      <td>CHN</td>
      <td>Asia</td>
    </tr>
    <tr>
      <th>16284</th>
      <td>1999</td>
      <td>Satellite Chemical</td>
      <td>Chemicals</td>
      <td>China</td>
      <td>4413.0</td>
      <td>931.3</td>
      <td>7640.0</td>
      <td>9521.0</td>
      <td>0.211036</td>
      <td>0.121898</td>
      <td>2022</td>
      <td>CHN</td>
      <td>Asia</td>
    </tr>
    <tr>
      <th>16285</th>
      <td>2000</td>
      <td>Sun Communities</td>
      <td>Diversified Financials</td>
      <td>United States</td>
      <td>2273.0</td>
      <td>375.7</td>
      <td>13494.0</td>
      <td>21714.0</td>
      <td>0.165288</td>
      <td>0.027842</td>
      <td>2022</td>
      <td>USA</td>
      <td>North America</td>
    </tr>
  </tbody>
</table>
<p>16284 rows × 13 columns</p>
</div>
      <button class="colab-df-convert" onclick="convertToInteractive('df-fc9b81fa-b53f-4837-8916-845ce7782d26')"
              title="Convert this dataframe to an interactive table."
              style="display:none;">

<svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
width="24px">
<path d="M0 0h24v24H0V0z" fill="none"/>
<path d="M18.56 5.44l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94zm-11 1L8.5 8.5l.94-2.06 2.06-.94-2.06-.94L8.5 2.5l-.94 2.06-2.06.94zm10 10l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94z"/><path d="M17.41 7.96l-1.37-1.37c-.4-.4-.92-.59-1.43-.59-.52 0-1.04.2-1.43.59L10.3 9.45l-7.72 7.72c-.78.78-.78 2.05 0 2.83L4 21.41c.39.39.9.59 1.41.59.51 0 1.02-.2 1.41-.59l7.78-7.78 2.81-2.81c.8-.78.8-2.07 0-2.86zM5.41 20L4 18.59l7.72-7.72 1.47 1.35L5.41 20z"/>
</svg>
</button>

  <style>
    .colab-df-container {
      display:flex;
      flex-wrap:wrap;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

      <script>
        const buttonEl =
          document.querySelector('#df-fc9b81fa-b53f-4837-8916-845ce7782d26 button.colab-df-convert');
        buttonEl.style.display =
          google.colab.kernel.accessAllowed ? 'block' : 'none';

        async function convertToInteractive(key) {
          const element = document.querySelector('#df-fc9b81fa-b53f-4837-8916-845ce7782d26');
          const dataTable =
            await google.colab.kernel.invokeFunction('convertToInteractive',
                                                     [key], {});
          if (!dataTable) return;

          const docLinkHtml = 'Like what you see? Visit the ' +
            '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
            + ' to learn more about interactive tables.';
          element.innerHTML = '';
          dataTable['output_type'] = 'display_data';
          await google.colab.output.renderOutput(dataTable, element);
          const docLink = document.createElement('div');
          docLink.innerHTML = docLinkHtml;
          element.appendChild(docLink);
        }
      </script>
    </div>

  </div>

```python
# Mostrar las primeras filas del dataframe
print(df_forbes_un.isna().sum())
df_forbes_un
```

    rank_nr                               0
    Empresa                               0
    Industria                             0
    Pais                                  0
    Ingresos                              8
    Ganancias                             2
    Activos                              14
    Valor de Mercado                      6
    Margen de Rentabilidad               10
    Rentabilidad de los Activos (ROA)    15
    Año                                   0
    Codigo                                0
    Continente                            0
    dtype: int64

  <div id="df-10f4d7de-a04e-4757-8215-62281397f6a9">
    <div class="colab-df-container">
      <div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }

</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>rank_nr</th>
      <th>Empresa</th>
      <th>Industria</th>
      <th>Pais</th>
      <th>Ingresos</th>
      <th>Ganancias</th>
      <th>Activos</th>
      <th>Valor de Mercado</th>
      <th>Margen de Rentabilidad</th>
      <th>Rentabilidad de los Activos (ROA)</th>
      <th>Año</th>
      <th>Codigo</th>
      <th>Continente</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>ICBC</td>
      <td>Banking</td>
      <td>China</td>
      <td>166796.0</td>
      <td>44757.2</td>
      <td>3322043.0</td>
      <td>278327.0</td>
      <td>0.268335</td>
      <td>0.013473</td>
      <td>2015</td>
      <td>CHN</td>
      <td>Asia</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2</td>
      <td>China Construction Bank</td>
      <td>Banking</td>
      <td>China</td>
      <td>130473.0</td>
      <td>37038.9</td>
      <td>2698925.0</td>
      <td>212945.0</td>
      <td>0.283882</td>
      <td>0.013724</td>
      <td>2015</td>
      <td>CHN</td>
      <td>Asia</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3</td>
      <td>Agricultural Bank of China</td>
      <td>Banking</td>
      <td>China</td>
      <td>129221.0</td>
      <td>29124.5</td>
      <td>2574815.0</td>
      <td>189879.0</td>
      <td>0.225385</td>
      <td>0.011311</td>
      <td>2015</td>
      <td>CHN</td>
      <td>Asia</td>
    </tr>
    <tr>
      <th>3</th>
      <td>4</td>
      <td>Bank of China</td>
      <td>Banking</td>
      <td>China</td>
      <td>120297.0</td>
      <td>27526.8</td>
      <td>2458336.0</td>
      <td>199130.0</td>
      <td>0.228824</td>
      <td>0.011197</td>
      <td>2015</td>
      <td>CHN</td>
      <td>Asia</td>
    </tr>
    <tr>
      <th>4</th>
      <td>5</td>
      <td>Berkshire Hathaway</td>
      <td>Diversified Financials</td>
      <td>United States</td>
      <td>194673.0</td>
      <td>19872.0</td>
      <td>534618.0</td>
      <td>354813.0</td>
      <td>0.102079</td>
      <td>0.037170</td>
      <td>2015</td>
      <td>USA</td>
      <td>North America</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>16281</th>
      <td>1995</td>
      <td>Shenzhen Feima International Supply Chain</td>
      <td>Business Services &amp; Supplies</td>
      <td>China</td>
      <td>37.0</td>
      <td>1408.3</td>
      <td>166.0</td>
      <td>1136.0</td>
      <td>38.062162</td>
      <td>8.483735</td>
      <td>2022</td>
      <td>CHN</td>
      <td>Asia</td>
    </tr>
    <tr>
      <th>16282</th>
      <td>1997</td>
      <td>NMDC</td>
      <td>Materials</td>
      <td>India</td>
      <td>3520.0</td>
      <td>1406.4</td>
      <td>5715.0</td>
      <td>6401.0</td>
      <td>0.399545</td>
      <td>0.246089</td>
      <td>2022</td>
      <td>IND</td>
      <td>Asia</td>
    </tr>
    <tr>
      <th>16283</th>
      <td>1997</td>
      <td>Sichuan Changhong Electric</td>
      <td>Consumer Durables</td>
      <td>China</td>
      <td>15716.0</td>
      <td>53.1</td>
      <td>12105.0</td>
      <td>1957.0</td>
      <td>0.003379</td>
      <td>0.004387</td>
      <td>2022</td>
      <td>CHN</td>
      <td>Asia</td>
    </tr>
    <tr>
      <th>16284</th>
      <td>1999</td>
      <td>Satellite Chemical</td>
      <td>Chemicals</td>
      <td>China</td>
      <td>4413.0</td>
      <td>931.3</td>
      <td>7640.0</td>
      <td>9521.0</td>
      <td>0.211036</td>
      <td>0.121898</td>
      <td>2022</td>
      <td>CHN</td>
      <td>Asia</td>
    </tr>
    <tr>
      <th>16285</th>
      <td>2000</td>
      <td>Sun Communities</td>
      <td>Diversified Financials</td>
      <td>United States</td>
      <td>2273.0</td>
      <td>375.7</td>
      <td>13494.0</td>
      <td>21714.0</td>
      <td>0.165288</td>
      <td>0.027842</td>
      <td>2022</td>
      <td>USA</td>
      <td>North America</td>
    </tr>
  </tbody>
</table>
<p>16284 rows × 13 columns</p>
</div>
      <button class="colab-df-convert" onclick="convertToInteractive('df-10f4d7de-a04e-4757-8215-62281397f6a9')"
              title="Convert this dataframe to an interactive table."
              style="display:none;">

<svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
width="24px">
<path d="M0 0h24v24H0V0z" fill="none"/>
<path d="M18.56 5.44l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94zm-11 1L8.5 8.5l.94-2.06 2.06-.94-2.06-.94L8.5 2.5l-.94 2.06-2.06.94zm10 10l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94z"/><path d="M17.41 7.96l-1.37-1.37c-.4-.4-.92-.59-1.43-.59-.52 0-1.04.2-1.43.59L10.3 9.45l-7.72 7.72c-.78.78-.78 2.05 0 2.83L4 21.41c.39.39.9.59 1.41.59.51 0 1.02-.2 1.41-.59l7.78-7.78 2.81-2.81c.8-.78.8-2.07 0-2.86zM5.41 20L4 18.59l7.72-7.72 1.47 1.35L5.41 20z"/>
</svg>
</button>

  <style>
    .colab-df-container {
      display:flex;
      flex-wrap:wrap;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

      <script>
        const buttonEl =
          document.querySelector('#df-10f4d7de-a04e-4757-8215-62281397f6a9 button.colab-df-convert');
        buttonEl.style.display =
          google.colab.kernel.accessAllowed ? 'block' : 'none';

        async function convertToInteractive(key) {
          const element = document.querySelector('#df-10f4d7de-a04e-4757-8215-62281397f6a9');
          const dataTable =
            await google.colab.kernel.invokeFunction('convertToInteractive',
                                                     [key], {});
          if (!dataTable) return;

          const docLinkHtml = 'Like what you see? Visit the ' +
            '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
            + ' to learn more about interactive tables.';
          element.innerHTML = '';
          dataTable['output_type'] = 'display_data';
          await google.colab.output.renderOutput(dataTable, element);
          const docLink = document.createElement('div');
          docLink.innerHTML = docLinkHtml;
          element.appendChild(docLink);
        }
      </script>
    </div>

  </div>

```python
import pandas as pd

# Mostrar las filas con valores nulos en la columna 'Rentabilidad de los Activos (ROA)'
df_vacias = df_forbes_un[df_forbes_un['Rentabilidad de los Activos (ROA)'].isnull()]
df_vacias
```

  <div id="df-fd9f3bce-4b4a-40a6-936f-4be6fc14adba">
    <div class="colab-df-container">
      <div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }

</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>rank_nr</th>
      <th>Empresa</th>
      <th>Industria</th>
      <th>Pais</th>
      <th>Ingresos</th>
      <th>Ganancias</th>
      <th>Activos</th>
      <th>Valor de Mercado</th>
      <th>Margen de Rentabilidad</th>
      <th>Rentabilidad de los Activos (ROA)</th>
      <th>Año</th>
      <th>Codigo</th>
      <th>Continente</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1966</th>
      <td>1927</td>
      <td>Shanghai Material Trading</td>
      <td>Trading Companies</td>
      <td>China</td>
      <td>12381.0</td>
      <td>6.2</td>
      <td>NaN</td>
      <td>908.0</td>
      <td>0.000501</td>
      <td>NaN</td>
      <td>2015</td>
      <td>CHN</td>
      <td>Asia</td>
    </tr>
    <tr>
      <th>3558</th>
      <td>1492</td>
      <td>Ambac Financial Group</td>
      <td>Insurance</td>
      <td>United States</td>
      <td>638.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>2016</td>
      <td>USA</td>
      <td>North America</td>
    </tr>
    <tr>
      <th>3915</th>
      <td>1840</td>
      <td>Banque nationale de Belgique</td>
      <td>Banking</td>
      <td>Belgium</td>
      <td>1742.0</td>
      <td>902.8</td>
      <td>NaN</td>
      <td>1343.0</td>
      <td>0.518255</td>
      <td>NaN</td>
      <td>2016</td>
      <td>BEL</td>
      <td>Europe</td>
    </tr>
    <tr>
      <th>5835</th>
      <td>1727</td>
      <td>Bank of Greece</td>
      <td>Banking</td>
      <td>Greece</td>
      <td>1935.0</td>
      <td>1208.4</td>
      <td>NaN</td>
      <td>240.0</td>
      <td>0.624496</td>
      <td>NaN</td>
      <td>2017</td>
      <td>GRC</td>
      <td>Europe</td>
    </tr>
    <tr>
      <th>6970</th>
      <td>842</td>
      <td>Infineon Technologies</td>
      <td>Semiconductors</td>
      <td>Germany</td>
      <td>8486.0</td>
      <td>1275.0</td>
      <td>NaN</td>
      <td>32351.0</td>
      <td>0.150247</td>
      <td>NaN</td>
      <td>2018</td>
      <td>DEU</td>
      <td>Europe</td>
    </tr>
    <tr>
      <th>7792</th>
      <td>1650</td>
      <td>IndusInd Bank</td>
      <td>Banking</td>
      <td>India</td>
      <td>2770.0</td>
      <td>427.7</td>
      <td>NaN</td>
      <td>16896.0</td>
      <td>0.154404</td>
      <td>NaN</td>
      <td>2018</td>
      <td>IND</td>
      <td>Asia</td>
    </tr>
    <tr>
      <th>8006</th>
      <td>1860</td>
      <td>Bank of Greece</td>
      <td>Banking</td>
      <td>Greece</td>
      <td>1679.0</td>
      <td>1062.3</td>
      <td>NaN</td>
      <td>354.0</td>
      <td>0.632698</td>
      <td>NaN</td>
      <td>2018</td>
      <td>GRC</td>
      <td>Europe</td>
    </tr>
    <tr>
      <th>8060</th>
      <td>1914</td>
      <td>Grupo Zuliano</td>
      <td>Chemicals</td>
      <td>Venezuela</td>
      <td>NaN</td>
      <td>998.9</td>
      <td>NaN</td>
      <td>139.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>2018</td>
      <td>VEN</td>
      <td>South America</td>
    </tr>
    <tr>
      <th>9142</th>
      <td>973</td>
      <td>Mahindra &amp; Mahindra</td>
      <td>Consumer Durables</td>
      <td>India</td>
      <td>15189.0</td>
      <td>833.0</td>
      <td>NaN</td>
      <td>12252.0</td>
      <td>0.054842</td>
      <td>NaN</td>
      <td>2019</td>
      <td>IND</td>
      <td>Asia</td>
    </tr>
    <tr>
      <th>9263</th>
      <td>1092</td>
      <td>SM Investments</td>
      <td>Retailing</td>
      <td>Philippines</td>
      <td>8538.0</td>
      <td>NaN</td>
      <td>18951.0</td>
      <td>21639.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>2019</td>
      <td>PHL</td>
      <td>Asia</td>
    </tr>
    <tr>
      <th>9628</th>
      <td>1453</td>
      <td>Chongqing Rural Bank</td>
      <td>Banking</td>
      <td>China</td>
      <td>6936.0</td>
      <td>1369.0</td>
      <td>NaN</td>
      <td>6144.0</td>
      <td>0.197376</td>
      <td>NaN</td>
      <td>2019</td>
      <td>CHN</td>
      <td>Asia</td>
    </tr>
    <tr>
      <th>9703</th>
      <td>1526</td>
      <td>Finatis</td>
      <td>Trading Companies</td>
      <td>France</td>
      <td>44249.0</td>
      <td>-92.0</td>
      <td>NaN</td>
      <td>260.0</td>
      <td>-0.002079</td>
      <td>NaN</td>
      <td>2019</td>
      <td>FRA</td>
      <td>Europe</td>
    </tr>
    <tr>
      <th>9994</th>
      <td>1812</td>
      <td>Yes Bank</td>
      <td>Banking</td>
      <td>India</td>
      <td>3965.0</td>
      <td>657.0</td>
      <td>NaN</td>
      <td>8523.0</td>
      <td>0.165700</td>
      <td>NaN</td>
      <td>2019</td>
      <td>IND</td>
      <td>Asia</td>
    </tr>
    <tr>
      <th>10159</th>
      <td>1977</td>
      <td>Drilling Company of 1972</td>
      <td>Oil &amp; Gas Operations</td>
      <td>Denmark</td>
      <td>1429.0</td>
      <td>941.0</td>
      <td>NaN</td>
      <td>3202.0</td>
      <td>0.658502</td>
      <td>NaN</td>
      <td>2019</td>
      <td>DNK</td>
      <td>Europe</td>
    </tr>
    <tr>
      <th>14182</th>
      <td>1933</td>
      <td>Bank of Greece</td>
      <td>Banking</td>
      <td>Greece</td>
      <td>1324.0</td>
      <td>942.8</td>
      <td>NaN</td>
      <td>366.0</td>
      <td>0.712085</td>
      <td>NaN</td>
      <td>2021</td>
      <td>GRC</td>
      <td>Europe</td>
    </tr>
  </tbody>
</table>
</div>
      <button class="colab-df-convert" onclick="convertToInteractive('df-fd9f3bce-4b4a-40a6-936f-4be6fc14adba')"
              title="Convert this dataframe to an interactive table."
              style="display:none;">

<svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
width="24px">
<path d="M0 0h24v24H0V0z" fill="none"/>
<path d="M18.56 5.44l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94zm-11 1L8.5 8.5l.94-2.06 2.06-.94-2.06-.94L8.5 2.5l-.94 2.06-2.06.94zm10 10l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94z"/><path d="M17.41 7.96l-1.37-1.37c-.4-.4-.92-.59-1.43-.59-.52 0-1.04.2-1.43.59L10.3 9.45l-7.72 7.72c-.78.78-.78 2.05 0 2.83L4 21.41c.39.39.9.59 1.41.59.51 0 1.02-.2 1.41-.59l7.78-7.78 2.81-2.81c.8-.78.8-2.07 0-2.86zM5.41 20L4 18.59l7.72-7.72 1.47 1.35L5.41 20z"/>
</svg>
</button>

  <style>
    .colab-df-container {
      display:flex;
      flex-wrap:wrap;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

      <script>
        const buttonEl =
          document.querySelector('#df-fd9f3bce-4b4a-40a6-936f-4be6fc14adba button.colab-df-convert');
        buttonEl.style.display =
          google.colab.kernel.accessAllowed ? 'block' : 'none';

        async function convertToInteractive(key) {
          const element = document.querySelector('#df-fd9f3bce-4b4a-40a6-936f-4be6fc14adba');
          const dataTable =
            await google.colab.kernel.invokeFunction('convertToInteractive',
                                                     [key], {});
          if (!dataTable) return;

          const docLinkHtml = 'Like what you see? Visit the ' +
            '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
            + ' to learn more about interactive tables.';
          element.innerHTML = '';
          dataTable['output_type'] = 'display_data';
          await google.colab.output.renderOutput(dataTable, element);
          const docLink = document.createElement('div');
          docLink.innerHTML = docLinkHtml;
          element.appendChild(docLink);
        }
      </script>
    </div>

  </div>

```python
import pandas as pd

# Eliminar las filas con valores nulos en la columna 'Rentabilidad de los Activos (ROA)'
df_forbes_un = df_forbes_un.dropna(subset=['Rentabilidad de los Activos (ROA)'])

# Mostrar las primeras filas del dataframe resultante
df_forbes_un
```

  <div id="df-a22d96c8-6d4f-458a-bbbe-dd48ed3127d4">
    <div class="colab-df-container">
      <div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }

</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>rank_nr</th>
      <th>Empresa</th>
      <th>Industria</th>
      <th>Pais</th>
      <th>Ingresos</th>
      <th>Ganancias</th>
      <th>Activos</th>
      <th>Valor de Mercado</th>
      <th>Margen de Rentabilidad</th>
      <th>Rentabilidad de los Activos (ROA)</th>
      <th>Año</th>
      <th>Codigo</th>
      <th>Continente</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>ICBC</td>
      <td>Banking</td>
      <td>China</td>
      <td>166796.0</td>
      <td>44757.2</td>
      <td>3322043.0</td>
      <td>278327.0</td>
      <td>0.268335</td>
      <td>0.013473</td>
      <td>2015</td>
      <td>CHN</td>
      <td>Asia</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2</td>
      <td>China Construction Bank</td>
      <td>Banking</td>
      <td>China</td>
      <td>130473.0</td>
      <td>37038.9</td>
      <td>2698925.0</td>
      <td>212945.0</td>
      <td>0.283882</td>
      <td>0.013724</td>
      <td>2015</td>
      <td>CHN</td>
      <td>Asia</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3</td>
      <td>Agricultural Bank of China</td>
      <td>Banking</td>
      <td>China</td>
      <td>129221.0</td>
      <td>29124.5</td>
      <td>2574815.0</td>
      <td>189879.0</td>
      <td>0.225385</td>
      <td>0.011311</td>
      <td>2015</td>
      <td>CHN</td>
      <td>Asia</td>
    </tr>
    <tr>
      <th>3</th>
      <td>4</td>
      <td>Bank of China</td>
      <td>Banking</td>
      <td>China</td>
      <td>120297.0</td>
      <td>27526.8</td>
      <td>2458336.0</td>
      <td>199130.0</td>
      <td>0.228824</td>
      <td>0.011197</td>
      <td>2015</td>
      <td>CHN</td>
      <td>Asia</td>
    </tr>
    <tr>
      <th>4</th>
      <td>5</td>
      <td>Berkshire Hathaway</td>
      <td>Diversified Financials</td>
      <td>United States</td>
      <td>194673.0</td>
      <td>19872.0</td>
      <td>534618.0</td>
      <td>354813.0</td>
      <td>0.102079</td>
      <td>0.037170</td>
      <td>2015</td>
      <td>USA</td>
      <td>North America</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>16281</th>
      <td>1995</td>
      <td>Shenzhen Feima International Supply Chain</td>
      <td>Business Services &amp; Supplies</td>
      <td>China</td>
      <td>37.0</td>
      <td>1408.3</td>
      <td>166.0</td>
      <td>1136.0</td>
      <td>38.062162</td>
      <td>8.483735</td>
      <td>2022</td>
      <td>CHN</td>
      <td>Asia</td>
    </tr>
    <tr>
      <th>16282</th>
      <td>1997</td>
      <td>NMDC</td>
      <td>Materials</td>
      <td>India</td>
      <td>3520.0</td>
      <td>1406.4</td>
      <td>5715.0</td>
      <td>6401.0</td>
      <td>0.399545</td>
      <td>0.246089</td>
      <td>2022</td>
      <td>IND</td>
      <td>Asia</td>
    </tr>
    <tr>
      <th>16283</th>
      <td>1997</td>
      <td>Sichuan Changhong Electric</td>
      <td>Consumer Durables</td>
      <td>China</td>
      <td>15716.0</td>
      <td>53.1</td>
      <td>12105.0</td>
      <td>1957.0</td>
      <td>0.003379</td>
      <td>0.004387</td>
      <td>2022</td>
      <td>CHN</td>
      <td>Asia</td>
    </tr>
    <tr>
      <th>16284</th>
      <td>1999</td>
      <td>Satellite Chemical</td>
      <td>Chemicals</td>
      <td>China</td>
      <td>4413.0</td>
      <td>931.3</td>
      <td>7640.0</td>
      <td>9521.0</td>
      <td>0.211036</td>
      <td>0.121898</td>
      <td>2022</td>
      <td>CHN</td>
      <td>Asia</td>
    </tr>
    <tr>
      <th>16285</th>
      <td>2000</td>
      <td>Sun Communities</td>
      <td>Diversified Financials</td>
      <td>United States</td>
      <td>2273.0</td>
      <td>375.7</td>
      <td>13494.0</td>
      <td>21714.0</td>
      <td>0.165288</td>
      <td>0.027842</td>
      <td>2022</td>
      <td>USA</td>
      <td>North America</td>
    </tr>
  </tbody>
</table>
<p>16269 rows × 13 columns</p>
</div>
      <button class="colab-df-convert" onclick="convertToInteractive('df-a22d96c8-6d4f-458a-bbbe-dd48ed3127d4')"
              title="Convert this dataframe to an interactive table."
              style="display:none;">

<svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
width="24px">
<path d="M0 0h24v24H0V0z" fill="none"/>
<path d="M18.56 5.44l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94zm-11 1L8.5 8.5l.94-2.06 2.06-.94-2.06-.94L8.5 2.5l-.94 2.06-2.06.94zm10 10l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94z"/><path d="M17.41 7.96l-1.37-1.37c-.4-.4-.92-.59-1.43-.59-.52 0-1.04.2-1.43.59L10.3 9.45l-7.72 7.72c-.78.78-.78 2.05 0 2.83L4 21.41c.39.39.9.59 1.41.59.51 0 1.02-.2 1.41-.59l7.78-7.78 2.81-2.81c.8-.78.8-2.07 0-2.86zM5.41 20L4 18.59l7.72-7.72 1.47 1.35L5.41 20z"/>
</svg>
</button>

  <style>
    .colab-df-container {
      display:flex;
      flex-wrap:wrap;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

      <script>
        const buttonEl =
          document.querySelector('#df-a22d96c8-6d4f-458a-bbbe-dd48ed3127d4 button.colab-df-convert');
        buttonEl.style.display =
          google.colab.kernel.accessAllowed ? 'block' : 'none';

        async function convertToInteractive(key) {
          const element = document.querySelector('#df-a22d96c8-6d4f-458a-bbbe-dd48ed3127d4');
          const dataTable =
            await google.colab.kernel.invokeFunction('convertToInteractive',
                                                     [key], {});
          if (!dataTable) return;

          const docLinkHtml = 'Like what you see? Visit the ' +
            '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
            + ' to learn more about interactive tables.';
          element.innerHTML = '';
          dataTable['output_type'] = 'display_data';
          await google.colab.output.renderOutput(dataTable, element);
          const docLink = document.createElement('div');
          docLink.innerHTML = docLinkHtml;
          element.appendChild(docLink);
        }
      </script>
    </div>

  </div>

```python
# Mostrar las primeras filas del dataframe
print(df_forbes_un.isna().sum())
df_forbes_un
```

    rank_nr                              0
    Empresa                              0
    Industria                            0
    Pais                                 0
    Ingresos                             7
    Ganancias                            0
    Activos                              0
    Valor de Mercado                     5
    Margen de Rentabilidad               7
    Rentabilidad de los Activos (ROA)    0
    Año                                  0
    Codigo                               0
    Continente                           0
    dtype: int64

  <div id="df-d17a2fe2-f28b-47b9-9183-ba11f6b6085b">
    <div class="colab-df-container">
      <div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }

</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>rank_nr</th>
      <th>Empresa</th>
      <th>Industria</th>
      <th>Pais</th>
      <th>Ingresos</th>
      <th>Ganancias</th>
      <th>Activos</th>
      <th>Valor de Mercado</th>
      <th>Margen de Rentabilidad</th>
      <th>Rentabilidad de los Activos (ROA)</th>
      <th>Año</th>
      <th>Codigo</th>
      <th>Continente</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>ICBC</td>
      <td>Banking</td>
      <td>China</td>
      <td>166796.0</td>
      <td>44757.2</td>
      <td>3322043.0</td>
      <td>278327.0</td>
      <td>0.268335</td>
      <td>0.013473</td>
      <td>2015</td>
      <td>CHN</td>
      <td>Asia</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2</td>
      <td>China Construction Bank</td>
      <td>Banking</td>
      <td>China</td>
      <td>130473.0</td>
      <td>37038.9</td>
      <td>2698925.0</td>
      <td>212945.0</td>
      <td>0.283882</td>
      <td>0.013724</td>
      <td>2015</td>
      <td>CHN</td>
      <td>Asia</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3</td>
      <td>Agricultural Bank of China</td>
      <td>Banking</td>
      <td>China</td>
      <td>129221.0</td>
      <td>29124.5</td>
      <td>2574815.0</td>
      <td>189879.0</td>
      <td>0.225385</td>
      <td>0.011311</td>
      <td>2015</td>
      <td>CHN</td>
      <td>Asia</td>
    </tr>
    <tr>
      <th>3</th>
      <td>4</td>
      <td>Bank of China</td>
      <td>Banking</td>
      <td>China</td>
      <td>120297.0</td>
      <td>27526.8</td>
      <td>2458336.0</td>
      <td>199130.0</td>
      <td>0.228824</td>
      <td>0.011197</td>
      <td>2015</td>
      <td>CHN</td>
      <td>Asia</td>
    </tr>
    <tr>
      <th>4</th>
      <td>5</td>
      <td>Berkshire Hathaway</td>
      <td>Diversified Financials</td>
      <td>United States</td>
      <td>194673.0</td>
      <td>19872.0</td>
      <td>534618.0</td>
      <td>354813.0</td>
      <td>0.102079</td>
      <td>0.037170</td>
      <td>2015</td>
      <td>USA</td>
      <td>North America</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>16281</th>
      <td>1995</td>
      <td>Shenzhen Feima International Supply Chain</td>
      <td>Business Services &amp; Supplies</td>
      <td>China</td>
      <td>37.0</td>
      <td>1408.3</td>
      <td>166.0</td>
      <td>1136.0</td>
      <td>38.062162</td>
      <td>8.483735</td>
      <td>2022</td>
      <td>CHN</td>
      <td>Asia</td>
    </tr>
    <tr>
      <th>16282</th>
      <td>1997</td>
      <td>NMDC</td>
      <td>Materials</td>
      <td>India</td>
      <td>3520.0</td>
      <td>1406.4</td>
      <td>5715.0</td>
      <td>6401.0</td>
      <td>0.399545</td>
      <td>0.246089</td>
      <td>2022</td>
      <td>IND</td>
      <td>Asia</td>
    </tr>
    <tr>
      <th>16283</th>
      <td>1997</td>
      <td>Sichuan Changhong Electric</td>
      <td>Consumer Durables</td>
      <td>China</td>
      <td>15716.0</td>
      <td>53.1</td>
      <td>12105.0</td>
      <td>1957.0</td>
      <td>0.003379</td>
      <td>0.004387</td>
      <td>2022</td>
      <td>CHN</td>
      <td>Asia</td>
    </tr>
    <tr>
      <th>16284</th>
      <td>1999</td>
      <td>Satellite Chemical</td>
      <td>Chemicals</td>
      <td>China</td>
      <td>4413.0</td>
      <td>931.3</td>
      <td>7640.0</td>
      <td>9521.0</td>
      <td>0.211036</td>
      <td>0.121898</td>
      <td>2022</td>
      <td>CHN</td>
      <td>Asia</td>
    </tr>
    <tr>
      <th>16285</th>
      <td>2000</td>
      <td>Sun Communities</td>
      <td>Diversified Financials</td>
      <td>United States</td>
      <td>2273.0</td>
      <td>375.7</td>
      <td>13494.0</td>
      <td>21714.0</td>
      <td>0.165288</td>
      <td>0.027842</td>
      <td>2022</td>
      <td>USA</td>
      <td>North America</td>
    </tr>
  </tbody>
</table>
<p>16269 rows × 13 columns</p>
</div>
      <button class="colab-df-convert" onclick="convertToInteractive('df-d17a2fe2-f28b-47b9-9183-ba11f6b6085b')"
              title="Convert this dataframe to an interactive table."
              style="display:none;">

<svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
width="24px">
<path d="M0 0h24v24H0V0z" fill="none"/>
<path d="M18.56 5.44l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94zm-11 1L8.5 8.5l.94-2.06 2.06-.94-2.06-.94L8.5 2.5l-.94 2.06-2.06.94zm10 10l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94z"/><path d="M17.41 7.96l-1.37-1.37c-.4-.4-.92-.59-1.43-.59-.52 0-1.04.2-1.43.59L10.3 9.45l-7.72 7.72c-.78.78-.78 2.05 0 2.83L4 21.41c.39.39.9.59 1.41.59.51 0 1.02-.2 1.41-.59l7.78-7.78 2.81-2.81c.8-.78.8-2.07 0-2.86zM5.41 20L4 18.59l7.72-7.72 1.47 1.35L5.41 20z"/>
</svg>
</button>

  <style>
    .colab-df-container {
      display:flex;
      flex-wrap:wrap;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

      <script>
        const buttonEl =
          document.querySelector('#df-d17a2fe2-f28b-47b9-9183-ba11f6b6085b button.colab-df-convert');
        buttonEl.style.display =
          google.colab.kernel.accessAllowed ? 'block' : 'none';

        async function convertToInteractive(key) {
          const element = document.querySelector('#df-d17a2fe2-f28b-47b9-9183-ba11f6b6085b');
          const dataTable =
            await google.colab.kernel.invokeFunction('convertToInteractive',
                                                     [key], {});
          if (!dataTable) return;

          const docLinkHtml = 'Like what you see? Visit the ' +
            '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
            + ' to learn more about interactive tables.';
          element.innerHTML = '';
          dataTable['output_type'] = 'display_data';
          await google.colab.output.renderOutput(dataTable, element);
          const docLink = document.createElement('div');
          docLink.innerHTML = docLinkHtml;
          element.appendChild(docLink);
        }
      </script>
    </div>

  </div>

```python
import pandas as pd

# Mostrar las filas con valores nulos en la columna 'Margen de Rentabilidad '
df_vacias = df_forbes_un[df_forbes_un['Margen de Rentabilidad'].isnull()]
df_vacias
```

  <div id="df-ce4440f4-44aa-49a9-992d-60757545b9f1">
    <div class="colab-df-container">
      <div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }

</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>rank_nr</th>
      <th>Empresa</th>
      <th>Industria</th>
      <th>Pais</th>
      <th>Ingresos</th>
      <th>Ganancias</th>
      <th>Activos</th>
      <th>Valor de Mercado</th>
      <th>Margen de Rentabilidad</th>
      <th>Rentabilidad de los Activos (ROA)</th>
      <th>Año</th>
      <th>Codigo</th>
      <th>Continente</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>706</th>
      <td>695</td>
      <td>Porsche Automobil Holding</td>
      <td>Consumer Durables</td>
      <td>Germany</td>
      <td>NaN</td>
      <td>4016.0</td>
      <td>36864.0</td>
      <td>15287.0</td>
      <td>NaN</td>
      <td>0.108941</td>
      <td>2015</td>
      <td>DEU</td>
      <td>Europe</td>
    </tr>
    <tr>
      <th>1516</th>
      <td>1489</td>
      <td>Dexia</td>
      <td>Banking</td>
      <td>Belgium</td>
      <td>NaN</td>
      <td>-803.8</td>
      <td>299028.0</td>
      <td>2352.0</td>
      <td>NaN</td>
      <td>-0.002688</td>
      <td>2015</td>
      <td>BEL</td>
      <td>Europe</td>
    </tr>
    <tr>
      <th>2724</th>
      <td>672</td>
      <td>Porsche Automobil Holding</td>
      <td>Consumer Durables</td>
      <td>Germany</td>
      <td>NaN</td>
      <td>3516.9</td>
      <td>34910.0</td>
      <td>16556.0</td>
      <td>NaN</td>
      <td>0.100742</td>
      <td>2016</td>
      <td>DEU</td>
      <td>Europe</td>
    </tr>
    <tr>
      <th>3132</th>
      <td>1072</td>
      <td>Kyushu Financial Group</td>
      <td>Banking</td>
      <td>Japan</td>
      <td>NaN</td>
      <td>812.3</td>
      <td>72979.0</td>
      <td>2640.0</td>
      <td>NaN</td>
      <td>0.011131</td>
      <td>2016</td>
      <td>JPN</td>
      <td>Asia</td>
    </tr>
    <tr>
      <th>3462</th>
      <td>1398</td>
      <td>RHB Capital</td>
      <td>Banking</td>
      <td>Malaysia</td>
      <td>NaN</td>
      <td>386.6</td>
      <td>53736.0</td>
      <td>4890.0</td>
      <td>NaN</td>
      <td>0.007194</td>
      <td>2016</td>
      <td>MYS</td>
      <td>Asia</td>
    </tr>
    <tr>
      <th>5906</th>
      <td>1796</td>
      <td>Grupo Zuliano</td>
      <td>Chemicals</td>
      <td>Venezuela</td>
      <td>NaN</td>
      <td>998.9</td>
      <td>1521.0</td>
      <td>72.0</td>
      <td>NaN</td>
      <td>0.656739</td>
      <td>2017</td>
      <td>VEN</td>
      <td>South America</td>
    </tr>
    <tr>
      <th>6026</th>
      <td>1914</td>
      <td>Technipfmc</td>
      <td>Oil &amp; Gas Operations</td>
      <td>United Kingdom</td>
      <td>NaN</td>
      <td>0.0</td>
      <td>1.0</td>
      <td>15631.0</td>
      <td>NaN</td>
      <td>0.000000</td>
      <td>2017</td>
      <td>GBR</td>
      <td>Europe</td>
    </tr>
  </tbody>
</table>
</div>
      <button class="colab-df-convert" onclick="convertToInteractive('df-ce4440f4-44aa-49a9-992d-60757545b9f1')"
              title="Convert this dataframe to an interactive table."
              style="display:none;">

<svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
width="24px">
<path d="M0 0h24v24H0V0z" fill="none"/>
<path d="M18.56 5.44l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94zm-11 1L8.5 8.5l.94-2.06 2.06-.94-2.06-.94L8.5 2.5l-.94 2.06-2.06.94zm10 10l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94z"/><path d="M17.41 7.96l-1.37-1.37c-.4-.4-.92-.59-1.43-.59-.52 0-1.04.2-1.43.59L10.3 9.45l-7.72 7.72c-.78.78-.78 2.05 0 2.83L4 21.41c.39.39.9.59 1.41.59.51 0 1.02-.2 1.41-.59l7.78-7.78 2.81-2.81c.8-.78.8-2.07 0-2.86zM5.41 20L4 18.59l7.72-7.72 1.47 1.35L5.41 20z"/>
</svg>
</button>

  <style>
    .colab-df-container {
      display:flex;
      flex-wrap:wrap;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

      <script>
        const buttonEl =
          document.querySelector('#df-ce4440f4-44aa-49a9-992d-60757545b9f1 button.colab-df-convert');
        buttonEl.style.display =
          google.colab.kernel.accessAllowed ? 'block' : 'none';

        async function convertToInteractive(key) {
          const element = document.querySelector('#df-ce4440f4-44aa-49a9-992d-60757545b9f1');
          const dataTable =
            await google.colab.kernel.invokeFunction('convertToInteractive',
                                                     [key], {});
          if (!dataTable) return;

          const docLinkHtml = 'Like what you see? Visit the ' +
            '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
            + ' to learn more about interactive tables.';
          element.innerHTML = '';
          dataTable['output_type'] = 'display_data';
          await google.colab.output.renderOutput(dataTable, element);
          const docLink = document.createElement('div');
          docLink.innerHTML = docLinkHtml;
          element.appendChild(docLink);
        }
      </script>
    </div>

  </div>

```python
import pandas as pd

# Eliminar las filas con valores nulos en la columna 'Rentabilidad de los Activos (ROA)'
df_forbes_un = df_forbes_un.dropna(subset=['Margen de Rentabilidad'])

# Mostrar las primeras filas del dataframe resultante
df_forbes_un
```

  <div id="df-c61edf95-11ea-424f-966a-3119c2184192">
    <div class="colab-df-container">
      <div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }

</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>rank_nr</th>
      <th>Empresa</th>
      <th>Industria</th>
      <th>Pais</th>
      <th>Ingresos</th>
      <th>Ganancias</th>
      <th>Activos</th>
      <th>Valor de Mercado</th>
      <th>Margen de Rentabilidad</th>
      <th>Rentabilidad de los Activos (ROA)</th>
      <th>Año</th>
      <th>Codigo</th>
      <th>Continente</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>ICBC</td>
      <td>Banking</td>
      <td>China</td>
      <td>166796.0</td>
      <td>44757.2</td>
      <td>3322043.0</td>
      <td>278327.0</td>
      <td>0.268335</td>
      <td>0.013473</td>
      <td>2015</td>
      <td>CHN</td>
      <td>Asia</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2</td>
      <td>China Construction Bank</td>
      <td>Banking</td>
      <td>China</td>
      <td>130473.0</td>
      <td>37038.9</td>
      <td>2698925.0</td>
      <td>212945.0</td>
      <td>0.283882</td>
      <td>0.013724</td>
      <td>2015</td>
      <td>CHN</td>
      <td>Asia</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3</td>
      <td>Agricultural Bank of China</td>
      <td>Banking</td>
      <td>China</td>
      <td>129221.0</td>
      <td>29124.5</td>
      <td>2574815.0</td>
      <td>189879.0</td>
      <td>0.225385</td>
      <td>0.011311</td>
      <td>2015</td>
      <td>CHN</td>
      <td>Asia</td>
    </tr>
    <tr>
      <th>3</th>
      <td>4</td>
      <td>Bank of China</td>
      <td>Banking</td>
      <td>China</td>
      <td>120297.0</td>
      <td>27526.8</td>
      <td>2458336.0</td>
      <td>199130.0</td>
      <td>0.228824</td>
      <td>0.011197</td>
      <td>2015</td>
      <td>CHN</td>
      <td>Asia</td>
    </tr>
    <tr>
      <th>4</th>
      <td>5</td>
      <td>Berkshire Hathaway</td>
      <td>Diversified Financials</td>
      <td>United States</td>
      <td>194673.0</td>
      <td>19872.0</td>
      <td>534618.0</td>
      <td>354813.0</td>
      <td>0.102079</td>
      <td>0.037170</td>
      <td>2015</td>
      <td>USA</td>
      <td>North America</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>16281</th>
      <td>1995</td>
      <td>Shenzhen Feima International Supply Chain</td>
      <td>Business Services &amp; Supplies</td>
      <td>China</td>
      <td>37.0</td>
      <td>1408.3</td>
      <td>166.0</td>
      <td>1136.0</td>
      <td>38.062162</td>
      <td>8.483735</td>
      <td>2022</td>
      <td>CHN</td>
      <td>Asia</td>
    </tr>
    <tr>
      <th>16282</th>
      <td>1997</td>
      <td>NMDC</td>
      <td>Materials</td>
      <td>India</td>
      <td>3520.0</td>
      <td>1406.4</td>
      <td>5715.0</td>
      <td>6401.0</td>
      <td>0.399545</td>
      <td>0.246089</td>
      <td>2022</td>
      <td>IND</td>
      <td>Asia</td>
    </tr>
    <tr>
      <th>16283</th>
      <td>1997</td>
      <td>Sichuan Changhong Electric</td>
      <td>Consumer Durables</td>
      <td>China</td>
      <td>15716.0</td>
      <td>53.1</td>
      <td>12105.0</td>
      <td>1957.0</td>
      <td>0.003379</td>
      <td>0.004387</td>
      <td>2022</td>
      <td>CHN</td>
      <td>Asia</td>
    </tr>
    <tr>
      <th>16284</th>
      <td>1999</td>
      <td>Satellite Chemical</td>
      <td>Chemicals</td>
      <td>China</td>
      <td>4413.0</td>
      <td>931.3</td>
      <td>7640.0</td>
      <td>9521.0</td>
      <td>0.211036</td>
      <td>0.121898</td>
      <td>2022</td>
      <td>CHN</td>
      <td>Asia</td>
    </tr>
    <tr>
      <th>16285</th>
      <td>2000</td>
      <td>Sun Communities</td>
      <td>Diversified Financials</td>
      <td>United States</td>
      <td>2273.0</td>
      <td>375.7</td>
      <td>13494.0</td>
      <td>21714.0</td>
      <td>0.165288</td>
      <td>0.027842</td>
      <td>2022</td>
      <td>USA</td>
      <td>North America</td>
    </tr>
  </tbody>
</table>
<p>16262 rows × 13 columns</p>
</div>
      <button class="colab-df-convert" onclick="convertToInteractive('df-c61edf95-11ea-424f-966a-3119c2184192')"
              title="Convert this dataframe to an interactive table."
              style="display:none;">

<svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
width="24px">
<path d="M0 0h24v24H0V0z" fill="none"/>
<path d="M18.56 5.44l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94zm-11 1L8.5 8.5l.94-2.06 2.06-.94-2.06-.94L8.5 2.5l-.94 2.06-2.06.94zm10 10l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94z"/><path d="M17.41 7.96l-1.37-1.37c-.4-.4-.92-.59-1.43-.59-.52 0-1.04.2-1.43.59L10.3 9.45l-7.72 7.72c-.78.78-.78 2.05 0 2.83L4 21.41c.39.39.9.59 1.41.59.51 0 1.02-.2 1.41-.59l7.78-7.78 2.81-2.81c.8-.78.8-2.07 0-2.86zM5.41 20L4 18.59l7.72-7.72 1.47 1.35L5.41 20z"/>
</svg>
</button>

  <style>
    .colab-df-container {
      display:flex;
      flex-wrap:wrap;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

      <script>
        const buttonEl =
          document.querySelector('#df-c61edf95-11ea-424f-966a-3119c2184192 button.colab-df-convert');
        buttonEl.style.display =
          google.colab.kernel.accessAllowed ? 'block' : 'none';

        async function convertToInteractive(key) {
          const element = document.querySelector('#df-c61edf95-11ea-424f-966a-3119c2184192');
          const dataTable =
            await google.colab.kernel.invokeFunction('convertToInteractive',
                                                     [key], {});
          if (!dataTable) return;

          const docLinkHtml = 'Like what you see? Visit the ' +
            '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
            + ' to learn more about interactive tables.';
          element.innerHTML = '';
          dataTable['output_type'] = 'display_data';
          await google.colab.output.renderOutput(dataTable, element);
          const docLink = document.createElement('div');
          docLink.innerHTML = docLinkHtml;
          element.appendChild(docLink);
        }
      </script>
    </div>

  </div>

```python
# Mostrar las primeras filas del dataframe
print(df_forbes_un.isna().sum())
df_forbes_un
```

    rank_nr                              0
    Empresa                              0
    Industria                            0
    Pais                                 0
    Ingresos                             0
    Ganancias                            0
    Activos                              0
    Valor de Mercado                     5
    Margen de Rentabilidad               0
    Rentabilidad de los Activos (ROA)    0
    Año                                  0
    Codigo                               0
    Continente                           0
    dtype: int64

  <div id="df-33cec3f5-f58f-4bb3-8a85-8a912aa693d8">
    <div class="colab-df-container">
      <div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }

</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>rank_nr</th>
      <th>Empresa</th>
      <th>Industria</th>
      <th>Pais</th>
      <th>Ingresos</th>
      <th>Ganancias</th>
      <th>Activos</th>
      <th>Valor de Mercado</th>
      <th>Margen de Rentabilidad</th>
      <th>Rentabilidad de los Activos (ROA)</th>
      <th>Año</th>
      <th>Codigo</th>
      <th>Continente</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>ICBC</td>
      <td>Banking</td>
      <td>China</td>
      <td>166796.0</td>
      <td>44757.2</td>
      <td>3322043.0</td>
      <td>278327.0</td>
      <td>0.268335</td>
      <td>0.013473</td>
      <td>2015</td>
      <td>CHN</td>
      <td>Asia</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2</td>
      <td>China Construction Bank</td>
      <td>Banking</td>
      <td>China</td>
      <td>130473.0</td>
      <td>37038.9</td>
      <td>2698925.0</td>
      <td>212945.0</td>
      <td>0.283882</td>
      <td>0.013724</td>
      <td>2015</td>
      <td>CHN</td>
      <td>Asia</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3</td>
      <td>Agricultural Bank of China</td>
      <td>Banking</td>
      <td>China</td>
      <td>129221.0</td>
      <td>29124.5</td>
      <td>2574815.0</td>
      <td>189879.0</td>
      <td>0.225385</td>
      <td>0.011311</td>
      <td>2015</td>
      <td>CHN</td>
      <td>Asia</td>
    </tr>
    <tr>
      <th>3</th>
      <td>4</td>
      <td>Bank of China</td>
      <td>Banking</td>
      <td>China</td>
      <td>120297.0</td>
      <td>27526.8</td>
      <td>2458336.0</td>
      <td>199130.0</td>
      <td>0.228824</td>
      <td>0.011197</td>
      <td>2015</td>
      <td>CHN</td>
      <td>Asia</td>
    </tr>
    <tr>
      <th>4</th>
      <td>5</td>
      <td>Berkshire Hathaway</td>
      <td>Diversified Financials</td>
      <td>United States</td>
      <td>194673.0</td>
      <td>19872.0</td>
      <td>534618.0</td>
      <td>354813.0</td>
      <td>0.102079</td>
      <td>0.037170</td>
      <td>2015</td>
      <td>USA</td>
      <td>North America</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>16281</th>
      <td>1995</td>
      <td>Shenzhen Feima International Supply Chain</td>
      <td>Business Services &amp; Supplies</td>
      <td>China</td>
      <td>37.0</td>
      <td>1408.3</td>
      <td>166.0</td>
      <td>1136.0</td>
      <td>38.062162</td>
      <td>8.483735</td>
      <td>2022</td>
      <td>CHN</td>
      <td>Asia</td>
    </tr>
    <tr>
      <th>16282</th>
      <td>1997</td>
      <td>NMDC</td>
      <td>Materials</td>
      <td>India</td>
      <td>3520.0</td>
      <td>1406.4</td>
      <td>5715.0</td>
      <td>6401.0</td>
      <td>0.399545</td>
      <td>0.246089</td>
      <td>2022</td>
      <td>IND</td>
      <td>Asia</td>
    </tr>
    <tr>
      <th>16283</th>
      <td>1997</td>
      <td>Sichuan Changhong Electric</td>
      <td>Consumer Durables</td>
      <td>China</td>
      <td>15716.0</td>
      <td>53.1</td>
      <td>12105.0</td>
      <td>1957.0</td>
      <td>0.003379</td>
      <td>0.004387</td>
      <td>2022</td>
      <td>CHN</td>
      <td>Asia</td>
    </tr>
    <tr>
      <th>16284</th>
      <td>1999</td>
      <td>Satellite Chemical</td>
      <td>Chemicals</td>
      <td>China</td>
      <td>4413.0</td>
      <td>931.3</td>
      <td>7640.0</td>
      <td>9521.0</td>
      <td>0.211036</td>
      <td>0.121898</td>
      <td>2022</td>
      <td>CHN</td>
      <td>Asia</td>
    </tr>
    <tr>
      <th>16285</th>
      <td>2000</td>
      <td>Sun Communities</td>
      <td>Diversified Financials</td>
      <td>United States</td>
      <td>2273.0</td>
      <td>375.7</td>
      <td>13494.0</td>
      <td>21714.0</td>
      <td>0.165288</td>
      <td>0.027842</td>
      <td>2022</td>
      <td>USA</td>
      <td>North America</td>
    </tr>
  </tbody>
</table>
<p>16262 rows × 13 columns</p>
</div>
      <button class="colab-df-convert" onclick="convertToInteractive('df-33cec3f5-f58f-4bb3-8a85-8a912aa693d8')"
              title="Convert this dataframe to an interactive table."
              style="display:none;">

<svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
width="24px">
<path d="M0 0h24v24H0V0z" fill="none"/>
<path d="M18.56 5.44l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94zm-11 1L8.5 8.5l.94-2.06 2.06-.94-2.06-.94L8.5 2.5l-.94 2.06-2.06.94zm10 10l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94z"/><path d="M17.41 7.96l-1.37-1.37c-.4-.4-.92-.59-1.43-.59-.52 0-1.04.2-1.43.59L10.3 9.45l-7.72 7.72c-.78.78-.78 2.05 0 2.83L4 21.41c.39.39.9.59 1.41.59.51 0 1.02-.2 1.41-.59l7.78-7.78 2.81-2.81c.8-.78.8-2.07 0-2.86zM5.41 20L4 18.59l7.72-7.72 1.47 1.35L5.41 20z"/>
</svg>
</button>

  <style>
    .colab-df-container {
      display:flex;
      flex-wrap:wrap;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

      <script>
        const buttonEl =
          document.querySelector('#df-33cec3f5-f58f-4bb3-8a85-8a912aa693d8 button.colab-df-convert');
        buttonEl.style.display =
          google.colab.kernel.accessAllowed ? 'block' : 'none';

        async function convertToInteractive(key) {
          const element = document.querySelector('#df-33cec3f5-f58f-4bb3-8a85-8a912aa693d8');
          const dataTable =
            await google.colab.kernel.invokeFunction('convertToInteractive',
                                                     [key], {});
          if (!dataTable) return;

          const docLinkHtml = 'Like what you see? Visit the ' +
            '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
            + ' to learn more about interactive tables.';
          element.innerHTML = '';
          dataTable['output_type'] = 'display_data';
          await google.colab.output.renderOutput(dataTable, element);
          const docLink = document.createElement('div');
          docLink.innerHTML = docLinkHtml;
          element.appendChild(docLink);
        }
      </script>
    </div>

  </div>

```python
import pandas as pd

# Eliminar las filas con valores nulos en la columna 'Valor de Mercado'
df_forbes_un = df_forbes_un.dropna(subset=['Valor de Mercado'])

# Mostrar las primeras filas del dataframe resultante
df_forbes_un
```

  <div id="df-7d69c9ef-ea8c-4990-8855-cd59506de807">
    <div class="colab-df-container">
      <div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }

</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>rank_nr</th>
      <th>Empresa</th>
      <th>Industria</th>
      <th>Pais</th>
      <th>Ingresos</th>
      <th>Ganancias</th>
      <th>Activos</th>
      <th>Valor de Mercado</th>
      <th>Margen de Rentabilidad</th>
      <th>Rentabilidad de los Activos (ROA)</th>
      <th>Año</th>
      <th>Codigo</th>
      <th>Continente</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>ICBC</td>
      <td>Banking</td>
      <td>China</td>
      <td>166796.0</td>
      <td>44757.2</td>
      <td>3322043.0</td>
      <td>278327.0</td>
      <td>0.268335</td>
      <td>0.013473</td>
      <td>2015</td>
      <td>CHN</td>
      <td>Asia</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2</td>
      <td>China Construction Bank</td>
      <td>Banking</td>
      <td>China</td>
      <td>130473.0</td>
      <td>37038.9</td>
      <td>2698925.0</td>
      <td>212945.0</td>
      <td>0.283882</td>
      <td>0.013724</td>
      <td>2015</td>
      <td>CHN</td>
      <td>Asia</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3</td>
      <td>Agricultural Bank of China</td>
      <td>Banking</td>
      <td>China</td>
      <td>129221.0</td>
      <td>29124.5</td>
      <td>2574815.0</td>
      <td>189879.0</td>
      <td>0.225385</td>
      <td>0.011311</td>
      <td>2015</td>
      <td>CHN</td>
      <td>Asia</td>
    </tr>
    <tr>
      <th>3</th>
      <td>4</td>
      <td>Bank of China</td>
      <td>Banking</td>
      <td>China</td>
      <td>120297.0</td>
      <td>27526.8</td>
      <td>2458336.0</td>
      <td>199130.0</td>
      <td>0.228824</td>
      <td>0.011197</td>
      <td>2015</td>
      <td>CHN</td>
      <td>Asia</td>
    </tr>
    <tr>
      <th>4</th>
      <td>5</td>
      <td>Berkshire Hathaway</td>
      <td>Diversified Financials</td>
      <td>United States</td>
      <td>194673.0</td>
      <td>19872.0</td>
      <td>534618.0</td>
      <td>354813.0</td>
      <td>0.102079</td>
      <td>0.037170</td>
      <td>2015</td>
      <td>USA</td>
      <td>North America</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>16281</th>
      <td>1995</td>
      <td>Shenzhen Feima International Supply Chain</td>
      <td>Business Services &amp; Supplies</td>
      <td>China</td>
      <td>37.0</td>
      <td>1408.3</td>
      <td>166.0</td>
      <td>1136.0</td>
      <td>38.062162</td>
      <td>8.483735</td>
      <td>2022</td>
      <td>CHN</td>
      <td>Asia</td>
    </tr>
    <tr>
      <th>16282</th>
      <td>1997</td>
      <td>NMDC</td>
      <td>Materials</td>
      <td>India</td>
      <td>3520.0</td>
      <td>1406.4</td>
      <td>5715.0</td>
      <td>6401.0</td>
      <td>0.399545</td>
      <td>0.246089</td>
      <td>2022</td>
      <td>IND</td>
      <td>Asia</td>
    </tr>
    <tr>
      <th>16283</th>
      <td>1997</td>
      <td>Sichuan Changhong Electric</td>
      <td>Consumer Durables</td>
      <td>China</td>
      <td>15716.0</td>
      <td>53.1</td>
      <td>12105.0</td>
      <td>1957.0</td>
      <td>0.003379</td>
      <td>0.004387</td>
      <td>2022</td>
      <td>CHN</td>
      <td>Asia</td>
    </tr>
    <tr>
      <th>16284</th>
      <td>1999</td>
      <td>Satellite Chemical</td>
      <td>Chemicals</td>
      <td>China</td>
      <td>4413.0</td>
      <td>931.3</td>
      <td>7640.0</td>
      <td>9521.0</td>
      <td>0.211036</td>
      <td>0.121898</td>
      <td>2022</td>
      <td>CHN</td>
      <td>Asia</td>
    </tr>
    <tr>
      <th>16285</th>
      <td>2000</td>
      <td>Sun Communities</td>
      <td>Diversified Financials</td>
      <td>United States</td>
      <td>2273.0</td>
      <td>375.7</td>
      <td>13494.0</td>
      <td>21714.0</td>
      <td>0.165288</td>
      <td>0.027842</td>
      <td>2022</td>
      <td>USA</td>
      <td>North America</td>
    </tr>
  </tbody>
</table>
<p>16257 rows × 13 columns</p>
</div>
      <button class="colab-df-convert" onclick="convertToInteractive('df-7d69c9ef-ea8c-4990-8855-cd59506de807')"
              title="Convert this dataframe to an interactive table."
              style="display:none;">

<svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
width="24px">
<path d="M0 0h24v24H0V0z" fill="none"/>
<path d="M18.56 5.44l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94zm-11 1L8.5 8.5l.94-2.06 2.06-.94-2.06-.94L8.5 2.5l-.94 2.06-2.06.94zm10 10l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94z"/><path d="M17.41 7.96l-1.37-1.37c-.4-.4-.92-.59-1.43-.59-.52 0-1.04.2-1.43.59L10.3 9.45l-7.72 7.72c-.78.78-.78 2.05 0 2.83L4 21.41c.39.39.9.59 1.41.59.51 0 1.02-.2 1.41-.59l7.78-7.78 2.81-2.81c.8-.78.8-2.07 0-2.86zM5.41 20L4 18.59l7.72-7.72 1.47 1.35L5.41 20z"/>
</svg>
</button>

  <style>
    .colab-df-container {
      display:flex;
      flex-wrap:wrap;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

      <script>
        const buttonEl =
          document.querySelector('#df-7d69c9ef-ea8c-4990-8855-cd59506de807 button.colab-df-convert');
        buttonEl.style.display =
          google.colab.kernel.accessAllowed ? 'block' : 'none';

        async function convertToInteractive(key) {
          const element = document.querySelector('#df-7d69c9ef-ea8c-4990-8855-cd59506de807');
          const dataTable =
            await google.colab.kernel.invokeFunction('convertToInteractive',
                                                     [key], {});
          if (!dataTable) return;

          const docLinkHtml = 'Like what you see? Visit the ' +
            '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
            + ' to learn more about interactive tables.';
          element.innerHTML = '';
          dataTable['output_type'] = 'display_data';
          await google.colab.output.renderOutput(dataTable, element);
          const docLink = document.createElement('div');
          docLink.innerHTML = docLinkHtml;
          element.appendChild(docLink);
        }
      </script>
    </div>

  </div>

```python
# Mostrar las primeras filas del dataframe
print(df_forbes_un.isna().sum())
df_forbes_un
```

    rank_nr                              0
    Empresa                              0
    Industria                            0
    Pais                                 0
    Ingresos                             0
    Ganancias                            0
    Activos                              0
    Valor de Mercado                     0
    Margen de Rentabilidad               0
    Rentabilidad de los Activos (ROA)    0
    Año                                  0
    Codigo                               0
    Continente                           0
    dtype: int64

  <div id="df-c320ee2c-2a1f-4a52-90d8-d6b87a02f613">
    <div class="colab-df-container">
      <div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }

</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>rank_nr</th>
      <th>Empresa</th>
      <th>Industria</th>
      <th>Pais</th>
      <th>Ingresos</th>
      <th>Ganancias</th>
      <th>Activos</th>
      <th>Valor de Mercado</th>
      <th>Margen de Rentabilidad</th>
      <th>Rentabilidad de los Activos (ROA)</th>
      <th>Año</th>
      <th>Codigo</th>
      <th>Continente</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>ICBC</td>
      <td>Banking</td>
      <td>China</td>
      <td>166796.0</td>
      <td>44757.2</td>
      <td>3322043.0</td>
      <td>278327.0</td>
      <td>0.268335</td>
      <td>0.013473</td>
      <td>2015</td>
      <td>CHN</td>
      <td>Asia</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2</td>
      <td>China Construction Bank</td>
      <td>Banking</td>
      <td>China</td>
      <td>130473.0</td>
      <td>37038.9</td>
      <td>2698925.0</td>
      <td>212945.0</td>
      <td>0.283882</td>
      <td>0.013724</td>
      <td>2015</td>
      <td>CHN</td>
      <td>Asia</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3</td>
      <td>Agricultural Bank of China</td>
      <td>Banking</td>
      <td>China</td>
      <td>129221.0</td>
      <td>29124.5</td>
      <td>2574815.0</td>
      <td>189879.0</td>
      <td>0.225385</td>
      <td>0.011311</td>
      <td>2015</td>
      <td>CHN</td>
      <td>Asia</td>
    </tr>
    <tr>
      <th>3</th>
      <td>4</td>
      <td>Bank of China</td>
      <td>Banking</td>
      <td>China</td>
      <td>120297.0</td>
      <td>27526.8</td>
      <td>2458336.0</td>
      <td>199130.0</td>
      <td>0.228824</td>
      <td>0.011197</td>
      <td>2015</td>
      <td>CHN</td>
      <td>Asia</td>
    </tr>
    <tr>
      <th>4</th>
      <td>5</td>
      <td>Berkshire Hathaway</td>
      <td>Diversified Financials</td>
      <td>United States</td>
      <td>194673.0</td>
      <td>19872.0</td>
      <td>534618.0</td>
      <td>354813.0</td>
      <td>0.102079</td>
      <td>0.037170</td>
      <td>2015</td>
      <td>USA</td>
      <td>North America</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>16281</th>
      <td>1995</td>
      <td>Shenzhen Feima International Supply Chain</td>
      <td>Business Services &amp; Supplies</td>
      <td>China</td>
      <td>37.0</td>
      <td>1408.3</td>
      <td>166.0</td>
      <td>1136.0</td>
      <td>38.062162</td>
      <td>8.483735</td>
      <td>2022</td>
      <td>CHN</td>
      <td>Asia</td>
    </tr>
    <tr>
      <th>16282</th>
      <td>1997</td>
      <td>NMDC</td>
      <td>Materials</td>
      <td>India</td>
      <td>3520.0</td>
      <td>1406.4</td>
      <td>5715.0</td>
      <td>6401.0</td>
      <td>0.399545</td>
      <td>0.246089</td>
      <td>2022</td>
      <td>IND</td>
      <td>Asia</td>
    </tr>
    <tr>
      <th>16283</th>
      <td>1997</td>
      <td>Sichuan Changhong Electric</td>
      <td>Consumer Durables</td>
      <td>China</td>
      <td>15716.0</td>
      <td>53.1</td>
      <td>12105.0</td>
      <td>1957.0</td>
      <td>0.003379</td>
      <td>0.004387</td>
      <td>2022</td>
      <td>CHN</td>
      <td>Asia</td>
    </tr>
    <tr>
      <th>16284</th>
      <td>1999</td>
      <td>Satellite Chemical</td>
      <td>Chemicals</td>
      <td>China</td>
      <td>4413.0</td>
      <td>931.3</td>
      <td>7640.0</td>
      <td>9521.0</td>
      <td>0.211036</td>
      <td>0.121898</td>
      <td>2022</td>
      <td>CHN</td>
      <td>Asia</td>
    </tr>
    <tr>
      <th>16285</th>
      <td>2000</td>
      <td>Sun Communities</td>
      <td>Diversified Financials</td>
      <td>United States</td>
      <td>2273.0</td>
      <td>375.7</td>
      <td>13494.0</td>
      <td>21714.0</td>
      <td>0.165288</td>
      <td>0.027842</td>
      <td>2022</td>
      <td>USA</td>
      <td>North America</td>
    </tr>
  </tbody>
</table>
<p>16257 rows × 13 columns</p>
</div>
      <button class="colab-df-convert" onclick="convertToInteractive('df-c320ee2c-2a1f-4a52-90d8-d6b87a02f613')"
              title="Convert this dataframe to an interactive table."
              style="display:none;">

<svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
width="24px">
<path d="M0 0h24v24H0V0z" fill="none"/>
<path d="M18.56 5.44l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94zm-11 1L8.5 8.5l.94-2.06 2.06-.94-2.06-.94L8.5 2.5l-.94 2.06-2.06.94zm10 10l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94z"/><path d="M17.41 7.96l-1.37-1.37c-.4-.4-.92-.59-1.43-.59-.52 0-1.04.2-1.43.59L10.3 9.45l-7.72 7.72c-.78.78-.78 2.05 0 2.83L4 21.41c.39.39.9.59 1.41.59.51 0 1.02-.2 1.41-.59l7.78-7.78 2.81-2.81c.8-.78.8-2.07 0-2.86zM5.41 20L4 18.59l7.72-7.72 1.47 1.35L5.41 20z"/>
</svg>
</button>

  <style>
    .colab-df-container {
      display:flex;
      flex-wrap:wrap;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

      <script>
        const buttonEl =
          document.querySelector('#df-c320ee2c-2a1f-4a52-90d8-d6b87a02f613 button.colab-df-convert');
        buttonEl.style.display =
          google.colab.kernel.accessAllowed ? 'block' : 'none';

        async function convertToInteractive(key) {
          const element = document.querySelector('#df-c320ee2c-2a1f-4a52-90d8-d6b87a02f613');
          const dataTable =
            await google.colab.kernel.invokeFunction('convertToInteractive',
                                                     [key], {});
          if (!dataTable) return;

          const docLinkHtml = 'Like what you see? Visit the ' +
            '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
            + ' to learn more about interactive tables.';
          element.innerHTML = '';
          dataTable['output_type'] = 'display_data';
          await google.colab.output.renderOutput(dataTable, element);
          const docLink = document.createElement('div');
          docLink.innerHTML = docLinkHtml;
          element.appendChild(docLink);
        }
      </script>
    </div>

  </div>

##Parte 2

###A. Vas a concatenar todos los datasets de Forbes 2000 desde el año 2015 hasta el año 2022.

```python
# Crear una copia del dataframe original
df_forbes_un_empresa = df_forbes_un.copy()

# Normalizar los nombres de la columna "Empresa" en la copia
df_forbes_un_empresa['Empresa'] = df_forbes_un_empresa['Empresa'].str.normalize('NFKD')\
                                                            .str.encode('ascii', errors='ignore')\
                                                            .str.decode('utf-8')\
                                                            .str.lower()

# Mostrar el dataframe sin advertencias
df_forbes_un_empresa
```

  <div id="df-7ab3dd40-19d2-4751-aa32-1ab5f7fc6acc">
    <div class="colab-df-container">
      <div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }

</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>rank_nr</th>
      <th>Empresa</th>
      <th>Industria</th>
      <th>Pais</th>
      <th>Ingresos</th>
      <th>Ganancias</th>
      <th>Activos</th>
      <th>Valor de Mercado</th>
      <th>Margen de Rentabilidad</th>
      <th>Rentabilidad de los Activos (ROA)</th>
      <th>Año</th>
      <th>Codigo</th>
      <th>Continente</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>icbc</td>
      <td>Banking</td>
      <td>China</td>
      <td>166796.0</td>
      <td>44757.2</td>
      <td>3322043.0</td>
      <td>278327.0</td>
      <td>0.268335</td>
      <td>0.013473</td>
      <td>2015</td>
      <td>CHN</td>
      <td>Asia</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2</td>
      <td>china construction bank</td>
      <td>Banking</td>
      <td>China</td>
      <td>130473.0</td>
      <td>37038.9</td>
      <td>2698925.0</td>
      <td>212945.0</td>
      <td>0.283882</td>
      <td>0.013724</td>
      <td>2015</td>
      <td>CHN</td>
      <td>Asia</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3</td>
      <td>agricultural bank of china</td>
      <td>Banking</td>
      <td>China</td>
      <td>129221.0</td>
      <td>29124.5</td>
      <td>2574815.0</td>
      <td>189879.0</td>
      <td>0.225385</td>
      <td>0.011311</td>
      <td>2015</td>
      <td>CHN</td>
      <td>Asia</td>
    </tr>
    <tr>
      <th>3</th>
      <td>4</td>
      <td>bank of china</td>
      <td>Banking</td>
      <td>China</td>
      <td>120297.0</td>
      <td>27526.8</td>
      <td>2458336.0</td>
      <td>199130.0</td>
      <td>0.228824</td>
      <td>0.011197</td>
      <td>2015</td>
      <td>CHN</td>
      <td>Asia</td>
    </tr>
    <tr>
      <th>4</th>
      <td>5</td>
      <td>berkshire hathaway</td>
      <td>Diversified Financials</td>
      <td>United States</td>
      <td>194673.0</td>
      <td>19872.0</td>
      <td>534618.0</td>
      <td>354813.0</td>
      <td>0.102079</td>
      <td>0.037170</td>
      <td>2015</td>
      <td>USA</td>
      <td>North America</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>16281</th>
      <td>1995</td>
      <td>shenzhen feima international supply chain</td>
      <td>Business Services &amp; Supplies</td>
      <td>China</td>
      <td>37.0</td>
      <td>1408.3</td>
      <td>166.0</td>
      <td>1136.0</td>
      <td>38.062162</td>
      <td>8.483735</td>
      <td>2022</td>
      <td>CHN</td>
      <td>Asia</td>
    </tr>
    <tr>
      <th>16282</th>
      <td>1997</td>
      <td>nmdc</td>
      <td>Materials</td>
      <td>India</td>
      <td>3520.0</td>
      <td>1406.4</td>
      <td>5715.0</td>
      <td>6401.0</td>
      <td>0.399545</td>
      <td>0.246089</td>
      <td>2022</td>
      <td>IND</td>
      <td>Asia</td>
    </tr>
    <tr>
      <th>16283</th>
      <td>1997</td>
      <td>sichuan changhong electric</td>
      <td>Consumer Durables</td>
      <td>China</td>
      <td>15716.0</td>
      <td>53.1</td>
      <td>12105.0</td>
      <td>1957.0</td>
      <td>0.003379</td>
      <td>0.004387</td>
      <td>2022</td>
      <td>CHN</td>
      <td>Asia</td>
    </tr>
    <tr>
      <th>16284</th>
      <td>1999</td>
      <td>satellite chemical</td>
      <td>Chemicals</td>
      <td>China</td>
      <td>4413.0</td>
      <td>931.3</td>
      <td>7640.0</td>
      <td>9521.0</td>
      <td>0.211036</td>
      <td>0.121898</td>
      <td>2022</td>
      <td>CHN</td>
      <td>Asia</td>
    </tr>
    <tr>
      <th>16285</th>
      <td>2000</td>
      <td>sun communities</td>
      <td>Diversified Financials</td>
      <td>United States</td>
      <td>2273.0</td>
      <td>375.7</td>
      <td>13494.0</td>
      <td>21714.0</td>
      <td>0.165288</td>
      <td>0.027842</td>
      <td>2022</td>
      <td>USA</td>
      <td>North America</td>
    </tr>
  </tbody>
</table>
<p>16257 rows × 13 columns</p>
</div>
      <button class="colab-df-convert" onclick="convertToInteractive('df-7ab3dd40-19d2-4751-aa32-1ab5f7fc6acc')"
              title="Convert this dataframe to an interactive table."
              style="display:none;">

<svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
width="24px">
<path d="M0 0h24v24H0V0z" fill="none"/>
<path d="M18.56 5.44l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94zm-11 1L8.5 8.5l.94-2.06 2.06-.94-2.06-.94L8.5 2.5l-.94 2.06-2.06.94zm10 10l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94z"/><path d="M17.41 7.96l-1.37-1.37c-.4-.4-.92-.59-1.43-.59-.52 0-1.04.2-1.43.59L10.3 9.45l-7.72 7.72c-.78.78-.78 2.05 0 2.83L4 21.41c.39.39.9.59 1.41.59.51 0 1.02-.2 1.41-.59l7.78-7.78 2.81-2.81c.8-.78.8-2.07 0-2.86zM5.41 20L4 18.59l7.72-7.72 1.47 1.35L5.41 20z"/>
</svg>
</button>

  <style>
    .colab-df-container {
      display:flex;
      flex-wrap:wrap;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

      <script>
        const buttonEl =
          document.querySelector('#df-7ab3dd40-19d2-4751-aa32-1ab5f7fc6acc button.colab-df-convert');
        buttonEl.style.display =
          google.colab.kernel.accessAllowed ? 'block' : 'none';

        async function convertToInteractive(key) {
          const element = document.querySelector('#df-7ab3dd40-19d2-4751-aa32-1ab5f7fc6acc');
          const dataTable =
            await google.colab.kernel.invokeFunction('convertToInteractive',
                                                     [key], {});
          if (!dataTable) return;

          const docLinkHtml = 'Like what you see? Visit the ' +
            '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
            + ' to learn more about interactive tables.';
          element.innerHTML = '';
          dataTable['output_type'] = 'display_data';
          await google.colab.output.renderOutput(dataTable, element);
          const docLink = document.createElement('div');
          docLink.innerHTML = docLinkHtml;
          element.appendChild(docLink);
        }
      </script>
    </div>

  </div>

###B. Tu nuevo dataframe debe contener 16000 filas x 13 columnas: `'Rank_nr', 'Empresa', 'Industria', 'Pais', 'Ingresos', 'Ganancias', 'Activos', 'Valor_Mercado', 'Ano', 'Margen_Rentabilidad', 'ROA', 'Continente', 'Codigo'`

```python
import pandas as pd

# Crear un diccionario con las variables que deseamos combinar
dict_anos_for = {'ano_500_2015': ano_500_2015, 'ano_500_2016': ano_500_2016, 'ano_500_2017': ano_500_2017,
                'ano_500_2018': ano_500_2018, 'ano_500_2019': ano_500_2019, 'ano_500_2020': ano_500_2020,
                'ano_500_2021': ano_500_2021, 'ano_500_2022': ano_500_2022}

# Concatenar los dataframes del diccionario en uno solo
df_fortune_un = pd.concat(dict_anos_for.values())

# Mostrar las primeras filas del dataframe resultante
df_fortune_un
```

  <div id="df-5803368c-5599-4435-8edf-036ed7acb291">
    <div class="colab-df-container">
      <div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }

</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Empresa</th>
      <th>Empleados</th>
      <th>Año</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Walmart</td>
      <td>2200000</td>
      <td>2015</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Sinopec Group</td>
      <td>897488</td>
      <td>2015</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Royal Dutch Shell</td>
      <td>94000</td>
      <td>2015</td>
    </tr>
    <tr>
      <th>3</th>
      <td>China National Petroleum</td>
      <td>1636532</td>
      <td>2015</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Exxon Mobil</td>
      <td>83700</td>
      <td>2015</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>495</th>
      <td>DSV</td>
      <td>77958</td>
      <td>2022</td>
    </tr>
    <tr>
      <th>496</th>
      <td>ABB</td>
      <td>104400</td>
      <td>2022</td>
    </tr>
    <tr>
      <th>497</th>
      <td>Mondelez International</td>
      <td>79000</td>
      <td>2022</td>
    </tr>
    <tr>
      <th>498</th>
      <td>Danone</td>
      <td>98105</td>
      <td>2022</td>
    </tr>
    <tr>
      <th>499</th>
      <td>Umicore</td>
      <td>11050</td>
      <td>2022</td>
    </tr>
  </tbody>
</table>
<p>4001 rows × 3 columns</p>
</div>
      <button class="colab-df-convert" onclick="convertToInteractive('df-5803368c-5599-4435-8edf-036ed7acb291')"
              title="Convert this dataframe to an interactive table."
              style="display:none;">

<svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
width="24px">
<path d="M0 0h24v24H0V0z" fill="none"/>
<path d="M18.56 5.44l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94zm-11 1L8.5 8.5l.94-2.06 2.06-.94-2.06-.94L8.5 2.5l-.94 2.06-2.06.94zm10 10l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94z"/><path d="M17.41 7.96l-1.37-1.37c-.4-.4-.92-.59-1.43-.59-.52 0-1.04.2-1.43.59L10.3 9.45l-7.72 7.72c-.78.78-.78 2.05 0 2.83L4 21.41c.39.39.9.59 1.41.59.51 0 1.02-.2 1.41-.59l7.78-7.78 2.81-2.81c.8-.78.8-2.07 0-2.86zM5.41 20L4 18.59l7.72-7.72 1.47 1.35L5.41 20z"/>
</svg>
</button>

  <style>
    .colab-df-container {
      display:flex;
      flex-wrap:wrap;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

      <script>
        const buttonEl =
          document.querySelector('#df-5803368c-5599-4435-8edf-036ed7acb291 button.colab-df-convert');
        buttonEl.style.display =
          google.colab.kernel.accessAllowed ? 'block' : 'none';

        async function convertToInteractive(key) {
          const element = document.querySelector('#df-5803368c-5599-4435-8edf-036ed7acb291');
          const dataTable =
            await google.colab.kernel.invokeFunction('convertToInteractive',
                                                     [key], {});
          if (!dataTable) return;

          const docLinkHtml = 'Like what you see? Visit the ' +
            '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
            + ' to learn more about interactive tables.';
          element.innerHTML = '';
          dataTable['output_type'] = 'display_data';
          await google.colab.output.renderOutput(dataTable, element);
          const docLink = document.createElement('div');
          docLink.innerHTML = docLinkHtml;
          element.appendChild(docLink);
        }
      </script>
    </div>

  </div>

```python
# Crear una copia del dataframe original
df_fortune_un_empresa = df_fortune_un.copy()

# Normalizar los nombres de la columna "Empresa" en la copia
df_fortune_un_empresa['Empresa'] = df_fortune_un_empresa['Empresa'].str.normalize('NFKD')\
                                                            .str.encode('ascii', errors='ignore')\
                                                            .str.decode('utf-8')\
                                                            .str.lower()

# Mostrar el dataframe sin advertencias
df_fortune_un_empresa
```

  <div id="df-2b65ba66-4799-4f9e-b5ea-e3dc2d2d3fb6">
    <div class="colab-df-container">
      <div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }

</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Empresa</th>
      <th>Empleados</th>
      <th>Año</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>walmart</td>
      <td>2200000</td>
      <td>2015</td>
    </tr>
    <tr>
      <th>1</th>
      <td>sinopec group</td>
      <td>897488</td>
      <td>2015</td>
    </tr>
    <tr>
      <th>2</th>
      <td>royal dutch shell</td>
      <td>94000</td>
      <td>2015</td>
    </tr>
    <tr>
      <th>3</th>
      <td>china national petroleum</td>
      <td>1636532</td>
      <td>2015</td>
    </tr>
    <tr>
      <th>4</th>
      <td>exxon mobil</td>
      <td>83700</td>
      <td>2015</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>495</th>
      <td>dsv</td>
      <td>77958</td>
      <td>2022</td>
    </tr>
    <tr>
      <th>496</th>
      <td>abb</td>
      <td>104400</td>
      <td>2022</td>
    </tr>
    <tr>
      <th>497</th>
      <td>mondelez international</td>
      <td>79000</td>
      <td>2022</td>
    </tr>
    <tr>
      <th>498</th>
      <td>danone</td>
      <td>98105</td>
      <td>2022</td>
    </tr>
    <tr>
      <th>499</th>
      <td>umicore</td>
      <td>11050</td>
      <td>2022</td>
    </tr>
  </tbody>
</table>
<p>4001 rows × 3 columns</p>
</div>
      <button class="colab-df-convert" onclick="convertToInteractive('df-2b65ba66-4799-4f9e-b5ea-e3dc2d2d3fb6')"
              title="Convert this dataframe to an interactive table."
              style="display:none;">

<svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
width="24px">
<path d="M0 0h24v24H0V0z" fill="none"/>
<path d="M18.56 5.44l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94zm-11 1L8.5 8.5l.94-2.06 2.06-.94-2.06-.94L8.5 2.5l-.94 2.06-2.06.94zm10 10l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94z"/><path d="M17.41 7.96l-1.37-1.37c-.4-.4-.92-.59-1.43-.59-.52 0-1.04.2-1.43.59L10.3 9.45l-7.72 7.72c-.78.78-.78 2.05 0 2.83L4 21.41c.39.39.9.59 1.41.59.51 0 1.02-.2 1.41-.59l7.78-7.78 2.81-2.81c.8-.78.8-2.07 0-2.86zM5.41 20L4 18.59l7.72-7.72 1.47 1.35L5.41 20z"/>
</svg>
</button>

  <style>
    .colab-df-container {
      display:flex;
      flex-wrap:wrap;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

      <script>
        const buttonEl =
          document.querySelector('#df-2b65ba66-4799-4f9e-b5ea-e3dc2d2d3fb6 button.colab-df-convert');
        buttonEl.style.display =
          google.colab.kernel.accessAllowed ? 'block' : 'none';

        async function convertToInteractive(key) {
          const element = document.querySelector('#df-2b65ba66-4799-4f9e-b5ea-e3dc2d2d3fb6');
          const dataTable =
            await google.colab.kernel.invokeFunction('convertToInteractive',
                                                     [key], {});
          if (!dataTable) return;

          const docLinkHtml = 'Like what you see? Visit the ' +
            '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
            + ' to learn more about interactive tables.';
          element.innerHTML = '';
          dataTable['output_type'] = 'display_data';
          await google.colab.output.renderOutput(dataTable, element);
          const docLink = document.createElement('div');
          docLink.innerHTML = docLinkHtml;
          element.appendChild(docLink);
        }
      </script>
    </div>

  </div>

##Parte 3

###A. Vas a hacer la junción de todos los datasets de Forbes 2000 desde el año 2015 hasta el año 2022 con los datasets de Fortune Global 500 que contienen únicamente 4000 filas y 3 columna: `'Ano', 'Empresa', 'Empleados'` . Observación: La junción con los datos de Forbes debe ser utilizando dos columnas como clave que serían `'Ano', 'Empresa'`, respectivamente.

```python
# Realizar la unión de los datasets de Forbes y Fortune
df_concat = pd.merge(df_forbes_un_empresa, df_fortune_un_empresa, on=['Año', 'Empresa'], how='inner')

# Mostrar las primeras filas del dataframe resultante
df_concat
```

  <div id="df-23574d3c-23cc-42ab-9f3f-6640a55e18f7">
    <div class="colab-df-container">
      <div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }

</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>rank_nr</th>
      <th>Empresa</th>
      <th>Industria</th>
      <th>Pais</th>
      <th>Ingresos</th>
      <th>Ganancias</th>
      <th>Activos</th>
      <th>Valor de Mercado</th>
      <th>Margen de Rentabilidad</th>
      <th>Rentabilidad de los Activos (ROA)</th>
      <th>Año</th>
      <th>Codigo</th>
      <th>Continente</th>
      <th>Empleados</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>2</td>
      <td>china construction bank</td>
      <td>Banking</td>
      <td>China</td>
      <td>130473.0</td>
      <td>37038.9</td>
      <td>2698925.0</td>
      <td>212945.0</td>
      <td>0.283882</td>
      <td>0.013724</td>
      <td>2015</td>
      <td>CHN</td>
      <td>Asia</td>
      <td>372321</td>
    </tr>
    <tr>
      <th>1</th>
      <td>3</td>
      <td>agricultural bank of china</td>
      <td>Banking</td>
      <td>China</td>
      <td>129221.0</td>
      <td>29124.5</td>
      <td>2574815.0</td>
      <td>189879.0</td>
      <td>0.225385</td>
      <td>0.011311</td>
      <td>2015</td>
      <td>CHN</td>
      <td>Asia</td>
      <td>505627</td>
    </tr>
    <tr>
      <th>2</th>
      <td>4</td>
      <td>bank of china</td>
      <td>Banking</td>
      <td>China</td>
      <td>120297.0</td>
      <td>27526.8</td>
      <td>2458336.0</td>
      <td>199130.0</td>
      <td>0.228824</td>
      <td>0.011197</td>
      <td>2015</td>
      <td>CHN</td>
      <td>Asia</td>
      <td>308128</td>
    </tr>
    <tr>
      <th>3</th>
      <td>5</td>
      <td>berkshire hathaway</td>
      <td>Diversified Financials</td>
      <td>United States</td>
      <td>194673.0</td>
      <td>19872.0</td>
      <td>534618.0</td>
      <td>354813.0</td>
      <td>0.102079</td>
      <td>0.037170</td>
      <td>2015</td>
      <td>USA</td>
      <td>North America</td>
      <td>316000</td>
    </tr>
    <tr>
      <th>4</th>
      <td>7</td>
      <td>exxon mobil</td>
      <td>Oil &amp; Gas Operations</td>
      <td>United States</td>
      <td>376240.0</td>
      <td>32520.0</td>
      <td>349493.0</td>
      <td>357094.0</td>
      <td>0.086434</td>
      <td>0.093049</td>
      <td>2015</td>
      <td>USA</td>
      <td>North America</td>
      <td>83700</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>2307</th>
      <td>1513</td>
      <td>performance food group</td>
      <td>Food Markets</td>
      <td>United States</td>
      <td>39732.0</td>
      <td>36.9</td>
      <td>12220.0</td>
      <td>8130.0</td>
      <td>0.000929</td>
      <td>0.003020</td>
      <td>2022</td>
      <td>USA</td>
      <td>North America</td>
      <td>22885</td>
    </tr>
    <tr>
      <th>2308</th>
      <td>1529</td>
      <td>us foods</td>
      <td>Food Markets</td>
      <td>United States</td>
      <td>29487.0</td>
      <td>164.0</td>
      <td>12521.0</td>
      <td>8523.0</td>
      <td>0.005562</td>
      <td>0.013098</td>
      <td>2022</td>
      <td>USA</td>
      <td>North America</td>
      <td>28000</td>
    </tr>
    <tr>
      <th>2309</th>
      <td>1548</td>
      <td>medipal holdings</td>
      <td>Drugs &amp; Biotechnology</td>
      <td>Japan</td>
      <td>29849.0</td>
      <td>331.4</td>
      <td>15444.0</td>
      <td>3349.0</td>
      <td>0.011103</td>
      <td>0.021458</td>
      <td>2022</td>
      <td>JPN</td>
      <td>Asia</td>
      <td>14454</td>
    </tr>
    <tr>
      <th>2310</th>
      <td>1640</td>
      <td>world fuel services</td>
      <td>Trading Companies</td>
      <td>United States</td>
      <td>31300.0</td>
      <td>73.6</td>
      <td>5942.0</td>
      <td>1715.0</td>
      <td>0.002351</td>
      <td>0.012386</td>
      <td>2022</td>
      <td>USA</td>
      <td>North America</td>
      <td>4414</td>
    </tr>
    <tr>
      <th>2311</th>
      <td>1656</td>
      <td>rajesh exports</td>
      <td>Consumer Durables</td>
      <td>India</td>
      <td>30005.0</td>
      <td>157.3</td>
      <td>2696.0</td>
      <td>2496.0</td>
      <td>0.005242</td>
      <td>0.058346</td>
      <td>2022</td>
      <td>IND</td>
      <td>Asia</td>
      <td>181</td>
    </tr>
  </tbody>
</table>
<p>2312 rows × 14 columns</p>
</div>
      <button class="colab-df-convert" onclick="convertToInteractive('df-23574d3c-23cc-42ab-9f3f-6640a55e18f7')"
              title="Convert this dataframe to an interactive table."
              style="display:none;">

<svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
width="24px">
<path d="M0 0h24v24H0V0z" fill="none"/>
<path d="M18.56 5.44l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94zm-11 1L8.5 8.5l.94-2.06 2.06-.94-2.06-.94L8.5 2.5l-.94 2.06-2.06.94zm10 10l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94z"/><path d="M17.41 7.96l-1.37-1.37c-.4-.4-.92-.59-1.43-.59-.52 0-1.04.2-1.43.59L10.3 9.45l-7.72 7.72c-.78.78-.78 2.05 0 2.83L4 21.41c.39.39.9.59 1.41.59.51 0 1.02-.2 1.41-.59l7.78-7.78 2.81-2.81c.8-.78.8-2.07 0-2.86zM5.41 20L4 18.59l7.72-7.72 1.47 1.35L5.41 20z"/>
</svg>
</button>

  <style>
    .colab-df-container {
      display:flex;
      flex-wrap:wrap;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

      <script>
        const buttonEl =
          document.querySelector('#df-23574d3c-23cc-42ab-9f3f-6640a55e18f7 button.colab-df-convert');
        buttonEl.style.display =
          google.colab.kernel.accessAllowed ? 'block' : 'none';

        async function convertToInteractive(key) {
          const element = document.querySelector('#df-23574d3c-23cc-42ab-9f3f-6640a55e18f7');
          const dataTable =
            await google.colab.kernel.invokeFunction('convertToInteractive',
                                                     [key], {});
          if (!dataTable) return;

          const docLinkHtml = 'Like what you see? Visit the ' +
            '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
            + ' to learn more about interactive tables.';
          element.innerHTML = '';
          dataTable['output_type'] = 'display_data';
          await google.colab.output.renderOutput(dataTable, element);
          const docLink = document.createElement('div');
          docLink.innerHTML = docLinkHtml;
          element.appendChild(docLink);
        }
      </script>
    </div>

  </div>

```python
# Convertir a minúsculas
df_concat['Industria'] = df_concat['Industria'].str.lower()

# Cambiar "telecommunications services" por una sola cadena
df_concat['Industria'] = df_concat['Industria'].replace('telecommunications services', 'telecommunication services')

df_concat
```

  <div id="df-555489ee-cc14-453a-a4a1-d2cc31edbec5">
    <div class="colab-df-container">
      <div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }

</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>rank_nr</th>
      <th>Empresa</th>
      <th>Industria</th>
      <th>Pais</th>
      <th>Ingresos</th>
      <th>Ganancias</th>
      <th>Activos</th>
      <th>Valor de Mercado</th>
      <th>Margen de Rentabilidad</th>
      <th>Rentabilidad de los Activos (ROA)</th>
      <th>Año</th>
      <th>Codigo</th>
      <th>Continente</th>
      <th>Empleados</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>2</td>
      <td>china construction bank</td>
      <td>banking</td>
      <td>China</td>
      <td>130473.0</td>
      <td>37038.9</td>
      <td>2698925.0</td>
      <td>212945.0</td>
      <td>0.283882</td>
      <td>0.013724</td>
      <td>2015</td>
      <td>CHN</td>
      <td>Asia</td>
      <td>372321</td>
    </tr>
    <tr>
      <th>1</th>
      <td>3</td>
      <td>agricultural bank of china</td>
      <td>banking</td>
      <td>China</td>
      <td>129221.0</td>
      <td>29124.5</td>
      <td>2574815.0</td>
      <td>189879.0</td>
      <td>0.225385</td>
      <td>0.011311</td>
      <td>2015</td>
      <td>CHN</td>
      <td>Asia</td>
      <td>505627</td>
    </tr>
    <tr>
      <th>2</th>
      <td>4</td>
      <td>bank of china</td>
      <td>banking</td>
      <td>China</td>
      <td>120297.0</td>
      <td>27526.8</td>
      <td>2458336.0</td>
      <td>199130.0</td>
      <td>0.228824</td>
      <td>0.011197</td>
      <td>2015</td>
      <td>CHN</td>
      <td>Asia</td>
      <td>308128</td>
    </tr>
    <tr>
      <th>3</th>
      <td>5</td>
      <td>berkshire hathaway</td>
      <td>diversified financials</td>
      <td>United States</td>
      <td>194673.0</td>
      <td>19872.0</td>
      <td>534618.0</td>
      <td>354813.0</td>
      <td>0.102079</td>
      <td>0.037170</td>
      <td>2015</td>
      <td>USA</td>
      <td>North America</td>
      <td>316000</td>
    </tr>
    <tr>
      <th>4</th>
      <td>7</td>
      <td>exxon mobil</td>
      <td>oil &amp; gas operations</td>
      <td>United States</td>
      <td>376240.0</td>
      <td>32520.0</td>
      <td>349493.0</td>
      <td>357094.0</td>
      <td>0.086434</td>
      <td>0.093049</td>
      <td>2015</td>
      <td>USA</td>
      <td>North America</td>
      <td>83700</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>2307</th>
      <td>1513</td>
      <td>performance food group</td>
      <td>food markets</td>
      <td>United States</td>
      <td>39732.0</td>
      <td>36.9</td>
      <td>12220.0</td>
      <td>8130.0</td>
      <td>0.000929</td>
      <td>0.003020</td>
      <td>2022</td>
      <td>USA</td>
      <td>North America</td>
      <td>22885</td>
    </tr>
    <tr>
      <th>2308</th>
      <td>1529</td>
      <td>us foods</td>
      <td>food markets</td>
      <td>United States</td>
      <td>29487.0</td>
      <td>164.0</td>
      <td>12521.0</td>
      <td>8523.0</td>
      <td>0.005562</td>
      <td>0.013098</td>
      <td>2022</td>
      <td>USA</td>
      <td>North America</td>
      <td>28000</td>
    </tr>
    <tr>
      <th>2309</th>
      <td>1548</td>
      <td>medipal holdings</td>
      <td>drugs &amp; biotechnology</td>
      <td>Japan</td>
      <td>29849.0</td>
      <td>331.4</td>
      <td>15444.0</td>
      <td>3349.0</td>
      <td>0.011103</td>
      <td>0.021458</td>
      <td>2022</td>
      <td>JPN</td>
      <td>Asia</td>
      <td>14454</td>
    </tr>
    <tr>
      <th>2310</th>
      <td>1640</td>
      <td>world fuel services</td>
      <td>trading companies</td>
      <td>United States</td>
      <td>31300.0</td>
      <td>73.6</td>
      <td>5942.0</td>
      <td>1715.0</td>
      <td>0.002351</td>
      <td>0.012386</td>
      <td>2022</td>
      <td>USA</td>
      <td>North America</td>
      <td>4414</td>
    </tr>
    <tr>
      <th>2311</th>
      <td>1656</td>
      <td>rajesh exports</td>
      <td>consumer durables</td>
      <td>India</td>
      <td>30005.0</td>
      <td>157.3</td>
      <td>2696.0</td>
      <td>2496.0</td>
      <td>0.005242</td>
      <td>0.058346</td>
      <td>2022</td>
      <td>IND</td>
      <td>Asia</td>
      <td>181</td>
    </tr>
  </tbody>
</table>
<p>2312 rows × 14 columns</p>
</div>
      <button class="colab-df-convert" onclick="convertToInteractive('df-555489ee-cc14-453a-a4a1-d2cc31edbec5')"
              title="Convert this dataframe to an interactive table."
              style="display:none;">

<svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
width="24px">
<path d="M0 0h24v24H0V0z" fill="none"/>
<path d="M18.56 5.44l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94zm-11 1L8.5 8.5l.94-2.06 2.06-.94-2.06-.94L8.5 2.5l-.94 2.06-2.06.94zm10 10l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94z"/><path d="M17.41 7.96l-1.37-1.37c-.4-.4-.92-.59-1.43-.59-.52 0-1.04.2-1.43.59L10.3 9.45l-7.72 7.72c-.78.78-.78 2.05 0 2.83L4 21.41c.39.39.9.59 1.41.59.51 0 1.02-.2 1.41-.59l7.78-7.78 2.81-2.81c.8-.78.8-2.07 0-2.86zM5.41 20L4 18.59l7.72-7.72 1.47 1.35L5.41 20z"/>
</svg>
</button>

  <style>
    .colab-df-container {
      display:flex;
      flex-wrap:wrap;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

      <script>
        const buttonEl =
          document.querySelector('#df-555489ee-cc14-453a-a4a1-d2cc31edbec5 button.colab-df-convert');
        buttonEl.style.display =
          google.colab.kernel.accessAllowed ? 'block' : 'none';

        async function convertToInteractive(key) {
          const element = document.querySelector('#df-555489ee-cc14-453a-a4a1-d2cc31edbec5');
          const dataTable =
            await google.colab.kernel.invokeFunction('convertToInteractive',
                                                     [key], {});
          if (!dataTable) return;

          const docLinkHtml = 'Like what you see? Visit the ' +
            '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
            + ' to learn more about interactive tables.';
          element.innerHTML = '';
          dataTable['output_type'] = 'display_data';
          await google.colab.output.renderOutput(dataTable, element);
          const docLink = document.createElement('div');
          docLink.innerHTML = docLinkHtml;
          element.appendChild(docLink);
        }
      </script>
    </div>

  </div>

###B. Como los rankings de Forbes y de Fortune son diferentes, vas a tener más del 80% de datos referentes a empleados faltantes. En este caso, únicamente vamos a trabajar con los datos que tienen correspondencia en ambas bases de datos. Se trata de alrededor 2200 registros de Forbes que tienen correspondencia con registros de Fortune que permiten tener la información sobre el número de empleados.

```python
# Realizar la unión de los datasets de Forbes y Fortune
df_merge = pd.merge(df_forbes_un, df_fortune_un, on=['Año', 'Empresa'], how='left', indicator=True)

# Mostrar las empresas que no tienen correspondencia en Forbes
df_missing = df_merge[df_merge['_merge'] == 'left_only']

# Mostrar las empresas que no tienen correspondencia en Forbes en un dataframe
df_empresas = pd.DataFrame(df_missing['Empresa'].unique(), columns=['Empresa'])
df_empresas = df_empresas.sort_values(by=['Empresa'])
df_empresas
```

  <div id="df-70cc4e69-9652-4efc-80d6-549b0150cb00">
    <div class="colab-df-container">
      <div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }

</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Empresa</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2292</th>
      <td>360 Security Technology</td>
    </tr>
    <tr>
      <th>1288</th>
      <td>3i Group</td>
    </tr>
    <tr>
      <th>1330</th>
      <td>77 Bank</td>
    </tr>
    <tr>
      <th>1609</th>
      <td>A2A</td>
    </tr>
    <tr>
      <th>1852</th>
      <td>AAC Technologies Holdings</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
    </tr>
    <tr>
      <th>365</th>
      <td>eBay</td>
    </tr>
    <tr>
      <th>2491</th>
      <td>iA Financial Corporation</td>
    </tr>
    <tr>
      <th>1705</th>
      <td>iHeartMedia</td>
    </tr>
    <tr>
      <th>2605</th>
      <td>iQIYI</td>
    </tr>
    <tr>
      <th>2967</th>
      <td>tesla</td>
    </tr>
  </tbody>
</table>
<p>3136 rows × 1 columns</p>
</div>
      <button class="colab-df-convert" onclick="convertToInteractive('df-70cc4e69-9652-4efc-80d6-549b0150cb00')"
              title="Convert this dataframe to an interactive table."
              style="display:none;">

<svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
width="24px">
<path d="M0 0h24v24H0V0z" fill="none"/>
<path d="M18.56 5.44l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94zm-11 1L8.5 8.5l.94-2.06 2.06-.94-2.06-.94L8.5 2.5l-.94 2.06-2.06.94zm10 10l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94z"/><path d="M17.41 7.96l-1.37-1.37c-.4-.4-.92-.59-1.43-.59-.52 0-1.04.2-1.43.59L10.3 9.45l-7.72 7.72c-.78.78-.78 2.05 0 2.83L4 21.41c.39.39.9.59 1.41.59.51 0 1.02-.2 1.41-.59l7.78-7.78 2.81-2.81c.8-.78.8-2.07 0-2.86zM5.41 20L4 18.59l7.72-7.72 1.47 1.35L5.41 20z"/>
</svg>
</button>

  <style>
    .colab-df-container {
      display:flex;
      flex-wrap:wrap;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

      <script>
        const buttonEl =
          document.querySelector('#df-70cc4e69-9652-4efc-80d6-549b0150cb00 button.colab-df-convert');
        buttonEl.style.display =
          google.colab.kernel.accessAllowed ? 'block' : 'none';

        async function convertToInteractive(key) {
          const element = document.querySelector('#df-70cc4e69-9652-4efc-80d6-549b0150cb00');
          const dataTable =
            await google.colab.kernel.invokeFunction('convertToInteractive',
                                                     [key], {});
          if (!dataTable) return;

          const docLinkHtml = 'Like what you see? Visit the ' +
            '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
            + ' to learn more about interactive tables.';
          element.innerHTML = '';
          dataTable['output_type'] = 'display_data';
          await google.colab.output.renderOutput(dataTable, element);
          const docLink = document.createElement('div');
          docLink.innerHTML = docLinkHtml;
          element.appendChild(docLink);
        }
      </script>
    </div>

  </div>

```python
# Mostrar las empresas que no tienen correspondencia en Forbes en un dataframe
df_emp = pd.DataFrame(df_concat['Empresa'].unique(), columns=['Empresa'])
df_emp = df_emp.sort_values(by=['Empresa'])
df_emp
```

  <div id="df-b02c8cfb-e98d-416e-972c-2343f4190c9c">
    <div class="colab-df-container">
      <div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }

</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Empresa</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>136</th>
      <td>3m</td>
    </tr>
    <tr>
      <th>134</th>
      <td>abb</td>
    </tr>
    <tr>
      <th>363</th>
      <td>abbott laboratories</td>
    </tr>
    <tr>
      <th>300</th>
      <td>abbvie</td>
    </tr>
    <tr>
      <th>186</th>
      <td>accenture</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
    </tr>
    <tr>
      <th>412</th>
      <td>x5 retail group</td>
    </tr>
    <tr>
      <th>353</th>
      <td>xiamen c&amp;d</td>
    </tr>
    <tr>
      <th>385</th>
      <td>xiaomi</td>
    </tr>
    <tr>
      <th>423</th>
      <td>zijin mining group</td>
    </tr>
    <tr>
      <th>49</th>
      <td>zurich insurance group</td>
    </tr>
  </tbody>
</table>
<p>448 rows × 1 columns</p>
</div>
      <button class="colab-df-convert" onclick="convertToInteractive('df-b02c8cfb-e98d-416e-972c-2343f4190c9c')"
              title="Convert this dataframe to an interactive table."
              style="display:none;">

<svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
width="24px">
<path d="M0 0h24v24H0V0z" fill="none"/>
<path d="M18.56 5.44l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94zm-11 1L8.5 8.5l.94-2.06 2.06-.94-2.06-.94L8.5 2.5l-.94 2.06-2.06.94zm10 10l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94z"/><path d="M17.41 7.96l-1.37-1.37c-.4-.4-.92-.59-1.43-.59-.52 0-1.04.2-1.43.59L10.3 9.45l-7.72 7.72c-.78.78-.78 2.05 0 2.83L4 21.41c.39.39.9.59 1.41.59.51 0 1.02-.2 1.41-.59l7.78-7.78 2.81-2.81c.8-.78.8-2.07 0-2.86zM5.41 20L4 18.59l7.72-7.72 1.47 1.35L5.41 20z"/>
</svg>
</button>

  <style>
    .colab-df-container {
      display:flex;
      flex-wrap:wrap;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

      <script>
        const buttonEl =
          document.querySelector('#df-b02c8cfb-e98d-416e-972c-2343f4190c9c button.colab-df-convert');
        buttonEl.style.display =
          google.colab.kernel.accessAllowed ? 'block' : 'none';

        async function convertToInteractive(key) {
          const element = document.querySelector('#df-b02c8cfb-e98d-416e-972c-2343f4190c9c');
          const dataTable =
            await google.colab.kernel.invokeFunction('convertToInteractive',
                                                     [key], {});
          if (!dataTable) return;

          const docLinkHtml = 'Like what you see? Visit the ' +
            '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
            + ' to learn more about interactive tables.';
          element.innerHTML = '';
          dataTable['output_type'] = 'display_data';
          await google.colab.output.renderOutput(dataTable, element);
          const docLink = document.createElement('div');
          docLink.innerHTML = docLinkHtml;
          element.appendChild(docLink);
        }
      </script>
    </div>

  </div>

```python
# Mostrar todas las Industrias
df_indus = pd.DataFrame(df_concat['Industria'].unique(), columns=['Industria'])
df_indus = df_indus.sort_values(by=['Industria'])
df_indus
```

  <div id="df-944fb6a9-1aad-41a5-9d58-0b37d85b60f6">
    <div class="colab-df-container">
      <div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }

</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Industria</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>16</th>
      <td>aerospace &amp; defense</td>
    </tr>
    <tr>
      <th>22</th>
      <td>air courier</td>
    </tr>
    <tr>
      <th>24</th>
      <td>airline</td>
    </tr>
    <tr>
      <th>0</th>
      <td>banking</td>
    </tr>
    <tr>
      <th>25</th>
      <td>business services &amp; supplies</td>
    </tr>
    <tr>
      <th>20</th>
      <td>capital goods</td>
    </tr>
    <tr>
      <th>15</th>
      <td>chemicals</td>
    </tr>
    <tr>
      <th>3</th>
      <td>conglomerates</td>
    </tr>
    <tr>
      <th>19</th>
      <td>construction</td>
    </tr>
    <tr>
      <th>4</th>
      <td>consumer durables</td>
    </tr>
    <tr>
      <th>1</th>
      <td>diversified financials</td>
    </tr>
    <tr>
      <th>13</th>
      <td>diversified metals &amp; mining</td>
    </tr>
    <tr>
      <th>12</th>
      <td>drugs &amp; biotechnology</td>
    </tr>
    <tr>
      <th>26</th>
      <td>food markets</td>
    </tr>
    <tr>
      <th>14</th>
      <td>food, drink &amp; tobacco</td>
    </tr>
    <tr>
      <th>10</th>
      <td>health care equipment &amp; services</td>
    </tr>
    <tr>
      <th>23</th>
      <td>hotels, restaurants &amp; leisure</td>
    </tr>
    <tr>
      <th>7</th>
      <td>insurance</td>
    </tr>
    <tr>
      <th>8</th>
      <td>it software &amp; services</td>
    </tr>
    <tr>
      <th>28</th>
      <td>materials</td>
    </tr>
    <tr>
      <th>11</th>
      <td>media</td>
    </tr>
    <tr>
      <th>2</th>
      <td>oil &amp; gas operations</td>
    </tr>
    <tr>
      <th>29</th>
      <td>real estate</td>
    </tr>
    <tr>
      <th>17</th>
      <td>retailing</td>
    </tr>
    <tr>
      <th>6</th>
      <td>semiconductors</td>
    </tr>
    <tr>
      <th>5</th>
      <td>technology hardware &amp; equipment</td>
    </tr>
    <tr>
      <th>9</th>
      <td>telecommunication services</td>
    </tr>
    <tr>
      <th>27</th>
      <td>trading companies</td>
    </tr>
    <tr>
      <th>21</th>
      <td>transportation</td>
    </tr>
    <tr>
      <th>18</th>
      <td>utilities</td>
    </tr>
  </tbody>
</table>
</div>
      <button class="colab-df-convert" onclick="convertToInteractive('df-944fb6a9-1aad-41a5-9d58-0b37d85b60f6')"
              title="Convert this dataframe to an interactive table."
              style="display:none;">

<svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
width="24px">
<path d="M0 0h24v24H0V0z" fill="none"/>
<path d="M18.56 5.44l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94zm-11 1L8.5 8.5l.94-2.06 2.06-.94-2.06-.94L8.5 2.5l-.94 2.06-2.06.94zm10 10l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94z"/><path d="M17.41 7.96l-1.37-1.37c-.4-.4-.92-.59-1.43-.59-.52 0-1.04.2-1.43.59L10.3 9.45l-7.72 7.72c-.78.78-.78 2.05 0 2.83L4 21.41c.39.39.9.59 1.41.59.51 0 1.02-.2 1.41-.59l7.78-7.78 2.81-2.81c.8-.78.8-2.07 0-2.86zM5.41 20L4 18.59l7.72-7.72 1.47 1.35L5.41 20z"/>
</svg>
</button>

  <style>
    .colab-df-container {
      display:flex;
      flex-wrap:wrap;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

      <script>
        const buttonEl =
          document.querySelector('#df-944fb6a9-1aad-41a5-9d58-0b37d85b60f6 button.colab-df-convert');
        buttonEl.style.display =
          google.colab.kernel.accessAllowed ? 'block' : 'none';

        async function convertToInteractive(key) {
          const element = document.querySelector('#df-944fb6a9-1aad-41a5-9d58-0b37d85b60f6');
          const dataTable =
            await google.colab.kernel.invokeFunction('convertToInteractive',
                                                     [key], {});
          if (!dataTable) return;

          const docLinkHtml = 'Like what you see? Visit the ' +
            '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
            + ' to learn more about interactive tables.';
          element.innerHTML = '';
          dataTable['output_type'] = 'display_data';
          await google.colab.output.renderOutput(dataTable, element);
          const docLink = document.createElement('div');
          docLink.innerHTML = docLinkHtml;
          element.appendChild(docLink);
        }
      </script>
    </div>

  </div>

```python
# Filtrar DataFrame original por "Russia"
df_russia = df_concat.loc[df_concat['Pais'] == 'Russia']

# Seleccionar columnas de interés
df_russia = df_russia[['Pais', 'Continente','Año']]

# Mostrar DataFrame filtrado
df_russia
```

  <div id="df-3b2f8fb5-03bd-4b6e-9554-a1c30c9a8392">
    <div class="colab-df-container">
      <div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }

</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Pais</th>
      <th>Continente</th>
      <th>Año</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>18</th>
      <td>Russia</td>
      <td>Europe</td>
      <td>2015</td>
    </tr>
    <tr>
      <th>19</th>
      <td>Russia</td>
      <td>Asia</td>
      <td>2015</td>
    </tr>
    <tr>
      <th>73</th>
      <td>Russia</td>
      <td>Europe</td>
      <td>2015</td>
    </tr>
    <tr>
      <th>74</th>
      <td>Russia</td>
      <td>Asia</td>
      <td>2015</td>
    </tr>
    <tr>
      <th>83</th>
      <td>Russia</td>
      <td>Europe</td>
      <td>2015</td>
    </tr>
    <tr>
      <th>84</th>
      <td>Russia</td>
      <td>Asia</td>
      <td>2015</td>
    </tr>
    <tr>
      <th>245</th>
      <td>Russia</td>
      <td>Europe</td>
      <td>2015</td>
    </tr>
    <tr>
      <th>246</th>
      <td>Russia</td>
      <td>Asia</td>
      <td>2015</td>
    </tr>
    <tr>
      <th>335</th>
      <td>Russia</td>
      <td>Europe</td>
      <td>2016</td>
    </tr>
    <tr>
      <th>336</th>
      <td>Russia</td>
      <td>Asia</td>
      <td>2016</td>
    </tr>
    <tr>
      <th>366</th>
      <td>Russia</td>
      <td>Europe</td>
      <td>2016</td>
    </tr>
    <tr>
      <th>367</th>
      <td>Russia</td>
      <td>Asia</td>
      <td>2016</td>
    </tr>
    <tr>
      <th>378</th>
      <td>Russia</td>
      <td>Europe</td>
      <td>2016</td>
    </tr>
    <tr>
      <th>379</th>
      <td>Russia</td>
      <td>Asia</td>
      <td>2016</td>
    </tr>
    <tr>
      <th>539</th>
      <td>Russia</td>
      <td>Europe</td>
      <td>2016</td>
    </tr>
    <tr>
      <th>540</th>
      <td>Russia</td>
      <td>Asia</td>
      <td>2016</td>
    </tr>
    <tr>
      <th>616</th>
      <td>Russia</td>
      <td>Europe</td>
      <td>2017</td>
    </tr>
    <tr>
      <th>617</th>
      <td>Russia</td>
      <td>Asia</td>
      <td>2017</td>
    </tr>
    <tr>
      <th>632</th>
      <td>Russia</td>
      <td>Europe</td>
      <td>2017</td>
    </tr>
    <tr>
      <th>633</th>
      <td>Russia</td>
      <td>Asia</td>
      <td>2017</td>
    </tr>
    <tr>
      <th>684</th>
      <td>Russia</td>
      <td>Europe</td>
      <td>2017</td>
    </tr>
    <tr>
      <th>685</th>
      <td>Russia</td>
      <td>Asia</td>
      <td>2017</td>
    </tr>
    <tr>
      <th>926</th>
      <td>Russia</td>
      <td>Europe</td>
      <td>2018</td>
    </tr>
    <tr>
      <th>927</th>
      <td>Russia</td>
      <td>Asia</td>
      <td>2018</td>
    </tr>
    <tr>
      <th>930</th>
      <td>Russia</td>
      <td>Europe</td>
      <td>2018</td>
    </tr>
    <tr>
      <th>931</th>
      <td>Russia</td>
      <td>Asia</td>
      <td>2018</td>
    </tr>
    <tr>
      <th>969</th>
      <td>Russia</td>
      <td>Europe</td>
      <td>2018</td>
    </tr>
    <tr>
      <th>970</th>
      <td>Russia</td>
      <td>Asia</td>
      <td>2018</td>
    </tr>
    <tr>
      <th>1227</th>
      <td>Russia</td>
      <td>Europe</td>
      <td>2019</td>
    </tr>
    <tr>
      <th>1228</th>
      <td>Russia</td>
      <td>Asia</td>
      <td>2019</td>
    </tr>
    <tr>
      <th>1231</th>
      <td>Russia</td>
      <td>Europe</td>
      <td>2019</td>
    </tr>
    <tr>
      <th>1232</th>
      <td>Russia</td>
      <td>Asia</td>
      <td>2019</td>
    </tr>
    <tr>
      <th>1267</th>
      <td>Russia</td>
      <td>Europe</td>
      <td>2019</td>
    </tr>
    <tr>
      <th>1268</th>
      <td>Russia</td>
      <td>Asia</td>
      <td>2019</td>
    </tr>
    <tr>
      <th>1507</th>
      <td>Russia</td>
      <td>Europe</td>
      <td>2020</td>
    </tr>
    <tr>
      <th>1508</th>
      <td>Russia</td>
      <td>Asia</td>
      <td>2020</td>
    </tr>
    <tr>
      <th>1552</th>
      <td>Russia</td>
      <td>Europe</td>
      <td>2020</td>
    </tr>
    <tr>
      <th>1553</th>
      <td>Russia</td>
      <td>Asia</td>
      <td>2020</td>
    </tr>
    <tr>
      <th>1680</th>
      <td>Russia</td>
      <td>Europe</td>
      <td>2020</td>
    </tr>
    <tr>
      <th>1681</th>
      <td>Russia</td>
      <td>Asia</td>
      <td>2020</td>
    </tr>
    <tr>
      <th>1797</th>
      <td>Russia</td>
      <td>Europe</td>
      <td>2021</td>
    </tr>
    <tr>
      <th>1798</th>
      <td>Russia</td>
      <td>Asia</td>
      <td>2021</td>
    </tr>
    <tr>
      <th>1939</th>
      <td>Russia</td>
      <td>Europe</td>
      <td>2021</td>
    </tr>
    <tr>
      <th>1940</th>
      <td>Russia</td>
      <td>Asia</td>
      <td>2021</td>
    </tr>
    <tr>
      <th>1967</th>
      <td>Russia</td>
      <td>Europe</td>
      <td>2021</td>
    </tr>
    <tr>
      <th>1968</th>
      <td>Russia</td>
      <td>Asia</td>
      <td>2021</td>
    </tr>
    <tr>
      <th>2026</th>
      <td>Russia</td>
      <td>Europe</td>
      <td>2021</td>
    </tr>
    <tr>
      <th>2027</th>
      <td>Russia</td>
      <td>Asia</td>
      <td>2021</td>
    </tr>
    <tr>
      <th>2071</th>
      <td>Russia</td>
      <td>Europe</td>
      <td>2022</td>
    </tr>
    <tr>
      <th>2072</th>
      <td>Russia</td>
      <td>Asia</td>
      <td>2022</td>
    </tr>
    <tr>
      <th>2118</th>
      <td>Russia</td>
      <td>Europe</td>
      <td>2022</td>
    </tr>
    <tr>
      <th>2119</th>
      <td>Russia</td>
      <td>Asia</td>
      <td>2022</td>
    </tr>
    <tr>
      <th>2146</th>
      <td>Russia</td>
      <td>Europe</td>
      <td>2022</td>
    </tr>
    <tr>
      <th>2147</th>
      <td>Russia</td>
      <td>Asia</td>
      <td>2022</td>
    </tr>
    <tr>
      <th>2304</th>
      <td>Russia</td>
      <td>Europe</td>
      <td>2022</td>
    </tr>
    <tr>
      <th>2305</th>
      <td>Russia</td>
      <td>Asia</td>
      <td>2022</td>
    </tr>
  </tbody>
</table>
</div>
      <button class="colab-df-convert" onclick="convertToInteractive('df-3b2f8fb5-03bd-4b6e-9554-a1c30c9a8392')"
              title="Convert this dataframe to an interactive table."
              style="display:none;">

<svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
width="24px">
<path d="M0 0h24v24H0V0z" fill="none"/>
<path d="M18.56 5.44l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94zm-11 1L8.5 8.5l.94-2.06 2.06-.94-2.06-.94L8.5 2.5l-.94 2.06-2.06.94zm10 10l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94z"/><path d="M17.41 7.96l-1.37-1.37c-.4-.4-.92-.59-1.43-.59-.52 0-1.04.2-1.43.59L10.3 9.45l-7.72 7.72c-.78.78-.78 2.05 0 2.83L4 21.41c.39.39.9.59 1.41.59.51 0 1.02-.2 1.41-.59l7.78-7.78 2.81-2.81c.8-.78.8-2.07 0-2.86zM5.41 20L4 18.59l7.72-7.72 1.47 1.35L5.41 20z"/>
</svg>
</button>

  <style>
    .colab-df-container {
      display:flex;
      flex-wrap:wrap;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

      <script>
        const buttonEl =
          document.querySelector('#df-3b2f8fb5-03bd-4b6e-9554-a1c30c9a8392 button.colab-df-convert');
        buttonEl.style.display =
          google.colab.kernel.accessAllowed ? 'block' : 'none';

        async function convertToInteractive(key) {
          const element = document.querySelector('#df-3b2f8fb5-03bd-4b6e-9554-a1c30c9a8392');
          const dataTable =
            await google.colab.kernel.invokeFunction('convertToInteractive',
                                                     [key], {});
          if (!dataTable) return;

          const docLinkHtml = 'Like what you see? Visit the ' +
            '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
            + ' to learn more about interactive tables.';
          element.innerHTML = '';
          dataTable['output_type'] = 'display_data';
          await google.colab.output.renderOutput(dataTable, element);
          const docLink = document.createElement('div');
          docLink.innerHTML = docLinkHtml;
          element.appendChild(docLink);
        }
      </script>
    </div>

  </div>

```python
# Filtrar DataFrame por el continente "Europe"
df_europe = df_concat.loc[df_concat['Continente'] == 'Europe']

# Eliminar filas correspondientes a "Russia" en la columna "Pais"
df_europe_sin_rusia = df_europe.loc[df_europe['Pais'] != 'Russia']

# Concatenar DataFrame filtrado con aquellas filas que no corresponden a "Europe"
df_concat = pd.concat([df_europe_sin_rusia, df_concat.loc[df_concat['Continente'] != 'Europe']])

# Mostrar DataFrame filtrado
df_concat
```

  <div id="df-f4f35d42-d8c9-4b30-94dd-b8995ffcf0a1">
    <div class="colab-df-container">
      <div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }

</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>rank_nr</th>
      <th>Empresa</th>
      <th>Industria</th>
      <th>Pais</th>
      <th>Ingresos</th>
      <th>Ganancias</th>
      <th>Activos</th>
      <th>Valor de Mercado</th>
      <th>Margen de Rentabilidad</th>
      <th>Rentabilidad de los Activos (ROA)</th>
      <th>Año</th>
      <th>Codigo</th>
      <th>Continente</th>
      <th>Empleados</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>9</th>
      <td>13</td>
      <td>royal dutch shell</td>
      <td>oil &amp; gas operations</td>
      <td>Netherlands</td>
      <td>420371.0</td>
      <td>14884.1</td>
      <td>353116.0</td>
      <td>195380.0</td>
      <td>0.035407</td>
      <td>0.042151</td>
      <td>2015</td>
      <td>NLD</td>
      <td>Europe</td>
      <td>94000</td>
    </tr>
    <tr>
      <th>10</th>
      <td>15</td>
      <td>hsbc holdings</td>
      <td>banking</td>
      <td>United Kingdom</td>
      <td>81086.0</td>
      <td>13536.7</td>
      <td>2634139.0</td>
      <td>167746.0</td>
      <td>0.166943</td>
      <td>0.005139</td>
      <td>2015</td>
      <td>GBR</td>
      <td>Europe</td>
      <td>264767</td>
    </tr>
    <tr>
      <th>14</th>
      <td>21</td>
      <td>allianz</td>
      <td>insurance</td>
      <td>Germany</td>
      <td>128401.0</td>
      <td>8250.5</td>
      <td>978980.0</td>
      <td>82007.0</td>
      <td>0.064256</td>
      <td>0.008428</td>
      <td>2015</td>
      <td>DEU</td>
      <td>Europe</td>
      <td>147425</td>
    </tr>
    <tr>
      <th>16</th>
      <td>26</td>
      <td>daimler</td>
      <td>consumer durables</td>
      <td>Germany</td>
      <td>172268.0</td>
      <td>9234.7</td>
      <td>229468.0</td>
      <td>103272.0</td>
      <td>0.053607</td>
      <td>0.040244</td>
      <td>2015</td>
      <td>DEU</td>
      <td>Europe</td>
      <td>279972</td>
    </tr>
    <tr>
      <th>20</th>
      <td>31</td>
      <td>banco santander</td>
      <td>banking</td>
      <td>Spain</td>
      <td>56361.0</td>
      <td>7714.6</td>
      <td>1532282.0</td>
      <td>109351.0</td>
      <td>0.136878</td>
      <td>0.005035</td>
      <td>2015</td>
      <td>ESP</td>
      <td>Europe</td>
      <td>185405</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>2307</th>
      <td>1513</td>
      <td>performance food group</td>
      <td>food markets</td>
      <td>United States</td>
      <td>39732.0</td>
      <td>36.9</td>
      <td>12220.0</td>
      <td>8130.0</td>
      <td>0.000929</td>
      <td>0.003020</td>
      <td>2022</td>
      <td>USA</td>
      <td>North America</td>
      <td>22885</td>
    </tr>
    <tr>
      <th>2308</th>
      <td>1529</td>
      <td>us foods</td>
      <td>food markets</td>
      <td>United States</td>
      <td>29487.0</td>
      <td>164.0</td>
      <td>12521.0</td>
      <td>8523.0</td>
      <td>0.005562</td>
      <td>0.013098</td>
      <td>2022</td>
      <td>USA</td>
      <td>North America</td>
      <td>28000</td>
    </tr>
    <tr>
      <th>2309</th>
      <td>1548</td>
      <td>medipal holdings</td>
      <td>drugs &amp; biotechnology</td>
      <td>Japan</td>
      <td>29849.0</td>
      <td>331.4</td>
      <td>15444.0</td>
      <td>3349.0</td>
      <td>0.011103</td>
      <td>0.021458</td>
      <td>2022</td>
      <td>JPN</td>
      <td>Asia</td>
      <td>14454</td>
    </tr>
    <tr>
      <th>2310</th>
      <td>1640</td>
      <td>world fuel services</td>
      <td>trading companies</td>
      <td>United States</td>
      <td>31300.0</td>
      <td>73.6</td>
      <td>5942.0</td>
      <td>1715.0</td>
      <td>0.002351</td>
      <td>0.012386</td>
      <td>2022</td>
      <td>USA</td>
      <td>North America</td>
      <td>4414</td>
    </tr>
    <tr>
      <th>2311</th>
      <td>1656</td>
      <td>rajesh exports</td>
      <td>consumer durables</td>
      <td>India</td>
      <td>30005.0</td>
      <td>157.3</td>
      <td>2696.0</td>
      <td>2496.0</td>
      <td>0.005242</td>
      <td>0.058346</td>
      <td>2022</td>
      <td>IND</td>
      <td>Asia</td>
      <td>181</td>
    </tr>
  </tbody>
</table>
<p>2284 rows × 14 columns</p>
</div>
      <button class="colab-df-convert" onclick="convertToInteractive('df-f4f35d42-d8c9-4b30-94dd-b8995ffcf0a1')"
              title="Convert this dataframe to an interactive table."
              style="display:none;">

<svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
width="24px">
<path d="M0 0h24v24H0V0z" fill="none"/>
<path d="M18.56 5.44l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94zm-11 1L8.5 8.5l.94-2.06 2.06-.94-2.06-.94L8.5 2.5l-.94 2.06-2.06.94zm10 10l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94z"/><path d="M17.41 7.96l-1.37-1.37c-.4-.4-.92-.59-1.43-.59-.52 0-1.04.2-1.43.59L10.3 9.45l-7.72 7.72c-.78.78-.78 2.05 0 2.83L4 21.41c.39.39.9.59 1.41.59.51 0 1.02-.2 1.41-.59l7.78-7.78 2.81-2.81c.8-.78.8-2.07 0-2.86zM5.41 20L4 18.59l7.72-7.72 1.47 1.35L5.41 20z"/>
</svg>
</button>

  <style>
    .colab-df-container {
      display:flex;
      flex-wrap:wrap;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

      <script>
        const buttonEl =
          document.querySelector('#df-f4f35d42-d8c9-4b30-94dd-b8995ffcf0a1 button.colab-df-convert');
        buttonEl.style.display =
          google.colab.kernel.accessAllowed ? 'block' : 'none';

        async function convertToInteractive(key) {
          const element = document.querySelector('#df-f4f35d42-d8c9-4b30-94dd-b8995ffcf0a1');
          const dataTable =
            await google.colab.kernel.invokeFunction('convertToInteractive',
                                                     [key], {});
          if (!dataTable) return;

          const docLinkHtml = 'Like what you see? Visit the ' +
            '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
            + ' to learn more about interactive tables.';
          element.innerHTML = '';
          dataTable['output_type'] = 'display_data';
          await google.colab.output.renderOutput(dataTable, element);
          const docLink = document.createElement('div');
          docLink.innerHTML = docLinkHtml;
          element.appendChild(docLink);
        }
      </script>
    </div>

  </div>

```python
# # Filtrar las filas con valores de ROA mayores a 0.1
# df_filtrado = df_concat.loc[df_concat['Rentabilidad de los Activos (ROA)'] >= 1]

# df_filtrado
```

#5. Consultas a los datos

##CUESTIONARIO A

Con los resultados de tus consultas a los datos, llegó la hora de poner en práctica tus conocimientos en [Matplotlib: Visualization with Python](https://matplotlib.org/) y [seaborn: statistical data visualization](https://seaborn.pydata.org/)

Debes generar una **gráfica para cada pregunta formulada**, utilizando todo el potencial que estas herramientas de visualización ofrecen. Establece un tamaño de lienzo de 15 x 8, un título, un subtítulo, los nombres a los ejes, leyenda, tamaño de fuente, una paleta de colores que facilite la visualización y que sea de tu gusto.

Dentro de los gráficos que vas a realizar, tendrás histogramas, gráficos de barras, gráficos de pizza, gráficos de dispersión, gráficos de línea, entre otros.

La idea es que explores y experimentes con todos los recursos que te brindan Matplotlib y Seaborn.

Las siguientes preguntas se refieren al ranking Forbes 2000 del año 2022:

###A. ¿Cuál es el Top 10 de países con más empresas en Forbes para el periodo indicado?

```python
import pandas as pd

# Filtrar para el año 2022
df_2022 = df_concat[df_concat['Año'] == '2022']
df_2022
```

  <div id="df-3a7102b4-b7af-4d55-a5c1-470e48b04ec6">
    <div class="colab-df-container">
      <div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }

</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>rank_nr</th>
      <th>Empresa</th>
      <th>Industria</th>
      <th>Pais</th>
      <th>Ingresos</th>
      <th>Ganancias</th>
      <th>Activos</th>
      <th>Valor de Mercado</th>
      <th>Margen de Rentabilidad</th>
      <th>Rentabilidad de los Activos (ROA)</th>
      <th>Año</th>
      <th>Codigo</th>
      <th>Continente</th>
      <th>Empleados</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2050</th>
      <td>16</td>
      <td>shell</td>
      <td>oil &amp; gas operations</td>
      <td>United Kingdom</td>
      <td>261761.0</td>
      <td>20265.4</td>
      <td>404379.0</td>
      <td>211096.0</td>
      <td>0.077419</td>
      <td>0.050115</td>
      <td>2022</td>
      <td>GBR</td>
      <td>Europe</td>
      <td>82000</td>
    </tr>
    <tr>
      <th>2062</th>
      <td>35</td>
      <td>allianz</td>
      <td>insurance</td>
      <td>Germany</td>
      <td>138617.0</td>
      <td>7812.9</td>
      <td>1324620.0</td>
      <td>96421.0</td>
      <td>0.056363</td>
      <td>0.005898</td>
      <td>2022</td>
      <td>DEU</td>
      <td>Europe</td>
      <td>155411</td>
    </tr>
    <tr>
      <th>2065</th>
      <td>38</td>
      <td>hsbc holdings</td>
      <td>banking</td>
      <td>United Kingdom</td>
      <td>59326.0</td>
      <td>12577.5</td>
      <td>2957939.0</td>
      <td>135300.0</td>
      <td>0.212007</td>
      <td>0.004252</td>
      <td>2022</td>
      <td>GBR</td>
      <td>Europe</td>
      <td>219697</td>
    </tr>
    <tr>
      <th>2066</th>
      <td>39</td>
      <td>bnp paribas</td>
      <td>banking</td>
      <td>France</td>
      <td>127425.0</td>
      <td>9848.3</td>
      <td>2995890.0</td>
      <td>68763.0</td>
      <td>0.077287</td>
      <td>0.003287</td>
      <td>2022</td>
      <td>FRA</td>
      <td>Europe</td>
      <td>189765</td>
    </tr>
    <tr>
      <th>2068</th>
      <td>41</td>
      <td>mercedes-benz group</td>
      <td>consumer durables</td>
      <td>Germany</td>
      <td>178935.0</td>
      <td>27192.7</td>
      <td>295480.0</td>
      <td>74621.0</td>
      <td>0.151970</td>
      <td>0.092029</td>
      <td>2022</td>
      <td>DEU</td>
      <td>Europe</td>
      <td>172425</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>2307</th>
      <td>1513</td>
      <td>performance food group</td>
      <td>food markets</td>
      <td>United States</td>
      <td>39732.0</td>
      <td>36.9</td>
      <td>12220.0</td>
      <td>8130.0</td>
      <td>0.000929</td>
      <td>0.003020</td>
      <td>2022</td>
      <td>USA</td>
      <td>North America</td>
      <td>22885</td>
    </tr>
    <tr>
      <th>2308</th>
      <td>1529</td>
      <td>us foods</td>
      <td>food markets</td>
      <td>United States</td>
      <td>29487.0</td>
      <td>164.0</td>
      <td>12521.0</td>
      <td>8523.0</td>
      <td>0.005562</td>
      <td>0.013098</td>
      <td>2022</td>
      <td>USA</td>
      <td>North America</td>
      <td>28000</td>
    </tr>
    <tr>
      <th>2309</th>
      <td>1548</td>
      <td>medipal holdings</td>
      <td>drugs &amp; biotechnology</td>
      <td>Japan</td>
      <td>29849.0</td>
      <td>331.4</td>
      <td>15444.0</td>
      <td>3349.0</td>
      <td>0.011103</td>
      <td>0.021458</td>
      <td>2022</td>
      <td>JPN</td>
      <td>Asia</td>
      <td>14454</td>
    </tr>
    <tr>
      <th>2310</th>
      <td>1640</td>
      <td>world fuel services</td>
      <td>trading companies</td>
      <td>United States</td>
      <td>31300.0</td>
      <td>73.6</td>
      <td>5942.0</td>
      <td>1715.0</td>
      <td>0.002351</td>
      <td>0.012386</td>
      <td>2022</td>
      <td>USA</td>
      <td>North America</td>
      <td>4414</td>
    </tr>
    <tr>
      <th>2311</th>
      <td>1656</td>
      <td>rajesh exports</td>
      <td>consumer durables</td>
      <td>India</td>
      <td>30005.0</td>
      <td>157.3</td>
      <td>2696.0</td>
      <td>2496.0</td>
      <td>0.005242</td>
      <td>0.058346</td>
      <td>2022</td>
      <td>IND</td>
      <td>Asia</td>
      <td>181</td>
    </tr>
  </tbody>
</table>
<p>270 rows × 14 columns</p>
</div>
      <button class="colab-df-convert" onclick="convertToInteractive('df-3a7102b4-b7af-4d55-a5c1-470e48b04ec6')"
              title="Convert this dataframe to an interactive table."
              style="display:none;">

<svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
width="24px">
<path d="M0 0h24v24H0V0z" fill="none"/>
<path d="M18.56 5.44l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94zm-11 1L8.5 8.5l.94-2.06 2.06-.94-2.06-.94L8.5 2.5l-.94 2.06-2.06.94zm10 10l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94z"/><path d="M17.41 7.96l-1.37-1.37c-.4-.4-.92-.59-1.43-.59-.52 0-1.04.2-1.43.59L10.3 9.45l-7.72 7.72c-.78.78-.78 2.05 0 2.83L4 21.41c.39.39.9.59 1.41.59.51 0 1.02-.2 1.41-.59l7.78-7.78 2.81-2.81c.8-.78.8-2.07 0-2.86zM5.41 20L4 18.59l7.72-7.72 1.47 1.35L5.41 20z"/>
</svg>
</button>

  <style>
    .colab-df-container {
      display:flex;
      flex-wrap:wrap;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

      <script>
        const buttonEl =
          document.querySelector('#df-3a7102b4-b7af-4d55-a5c1-470e48b04ec6 button.colab-df-convert');
        buttonEl.style.display =
          google.colab.kernel.accessAllowed ? 'block' : 'none';

        async function convertToInteractive(key) {
          const element = document.querySelector('#df-3a7102b4-b7af-4d55-a5c1-470e48b04ec6');
          const dataTable =
            await google.colab.kernel.invokeFunction('convertToInteractive',
                                                     [key], {});
          if (!dataTable) return;

          const docLinkHtml = 'Like what you see? Visit the ' +
            '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
            + ' to learn more about interactive tables.';
          element.innerHTML = '';
          dataTable['output_type'] = 'display_data';
          await google.colab.output.renderOutput(dataTable, element);
          const docLink = document.createElement('div');
          docLink.innerHTML = docLinkHtml;
          element.appendChild(docLink);
        }
      </script>
    </div>

  </div>

```python
import pandas as pd

# Obtener el Top 10 de países con más empresas
top_10_paises = pd.DataFrame(df_2022['Pais'].value_counts().head(10)).reset_index()

# Renombrar las columnas
top_10_paises = top_10_paises.rename(columns={'index': 'Pais', 'Pais': '#de Empresas'})

top_10_paises
```

  <div id="df-139e2719-abed-470a-b86f-d1143e8ce619">
    <div class="colab-df-container">
      <div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }

</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Pais</th>
      <th>#de Empresas</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>United States</td>
      <td>94</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Japan</td>
      <td>31</td>
    </tr>
    <tr>
      <th>2</th>
      <td>China</td>
      <td>27</td>
    </tr>
    <tr>
      <th>3</th>
      <td>United Kingdom</td>
      <td>15</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Canada</td>
      <td>13</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Germany</td>
      <td>13</td>
    </tr>
    <tr>
      <th>6</th>
      <td>France</td>
      <td>12</td>
    </tr>
    <tr>
      <th>7</th>
      <td>South Korea</td>
      <td>12</td>
    </tr>
    <tr>
      <th>8</th>
      <td>India</td>
      <td>8</td>
    </tr>
    <tr>
      <th>9</th>
      <td>Switzerland</td>
      <td>6</td>
    </tr>
  </tbody>
</table>
</div>
      <button class="colab-df-convert" onclick="convertToInteractive('df-139e2719-abed-470a-b86f-d1143e8ce619')"
              title="Convert this dataframe to an interactive table."
              style="display:none;">

<svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
width="24px">
<path d="M0 0h24v24H0V0z" fill="none"/>
<path d="M18.56 5.44l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94zm-11 1L8.5 8.5l.94-2.06 2.06-.94-2.06-.94L8.5 2.5l-.94 2.06-2.06.94zm10 10l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94z"/><path d="M17.41 7.96l-1.37-1.37c-.4-.4-.92-.59-1.43-.59-.52 0-1.04.2-1.43.59L10.3 9.45l-7.72 7.72c-.78.78-.78 2.05 0 2.83L4 21.41c.39.39.9.59 1.41.59.51 0 1.02-.2 1.41-.59l7.78-7.78 2.81-2.81c.8-.78.8-2.07 0-2.86zM5.41 20L4 18.59l7.72-7.72 1.47 1.35L5.41 20z"/>
</svg>
</button>

  <style>
    .colab-df-container {
      display:flex;
      flex-wrap:wrap;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

      <script>
        const buttonEl =
          document.querySelector('#df-139e2719-abed-470a-b86f-d1143e8ce619 button.colab-df-convert');
        buttonEl.style.display =
          google.colab.kernel.accessAllowed ? 'block' : 'none';

        async function convertToInteractive(key) {
          const element = document.querySelector('#df-139e2719-abed-470a-b86f-d1143e8ce619');
          const dataTable =
            await google.colab.kernel.invokeFunction('convertToInteractive',
                                                     [key], {});
          if (!dataTable) return;

          const docLinkHtml = 'Like what you see? Visit the ' +
            '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
            + ' to learn more about interactive tables.';
          element.innerHTML = '';
          dataTable['output_type'] = 'display_data';
          await google.colab.output.renderOutput(dataTable, element);
          const docLink = document.createElement('div');
          docLink.innerHTML = docLinkHtml;
          element.appendChild(docLink);
        }
      </script>
    </div>

  </div>

```python
import seaborn as sns
import matplotlib.pyplot as plt

# Crear la gráfica
sns.set(style='whitegrid')
plt.figure(figsize=(15,8))
plt.title('Top 10 Países con más Empresas', fontsize=20)
plt.xlabel('País', fontsize=16)
plt.ylabel('# de Empresas', fontsize=16)
sns.barplot(x='Pais', y='#de Empresas', data=top_10_paises, palette='Blues_d')
plt.xticks(fontsize=14, rotation=45)
plt.yticks(fontsize=14)
plt.tight_layout()
plt.show();
```

![png](Data_Insider_files/Data_Insider_66_0.png)

###B.¿Cuál es el Top 4 de países con más empresas en el área de tecnología y de telecomunicaciones?

```python
!pip install nbconvert##
```

  <div id="df-841d0f9a-7f16-43b2-aff5-f0b44d8f9adc">
    <div class="colab-df-container">
      <div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }

</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>+ Empresas</th>
    </tr>
    <tr>
      <th>Pais</th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>United States</th>
      <td>6</td>
    </tr>
    <tr>
      <th>Taiwan</th>
      <td>4</td>
    </tr>
    <tr>
      <th>Japan</th>
      <td>2</td>
    </tr>
    <tr>
      <th>Germany</th>
      <td>1</td>
    </tr>
  </tbody>
</table>
</div>
      <button class="colab-df-convert" onclick="convertToInteractive('df-841d0f9a-7f16-43b2-aff5-f0b44d8f9adc')"
              title="Convert this dataframe to an interactive table."
              style="display:none;">

<svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
width="24px">
<path d="M0 0h24v24H0V0z" fill="none"/>
<path d="M18.56 5.44l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94zm-11 1L8.5 8.5l.94-2.06 2.06-.94-2.06-.94L8.5 2.5l-.94 2.06-2.06.94zm10 10l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94z"/><path d="M17.41 7.96l-1.37-1.37c-.4-.4-.92-.59-1.43-.59-.52 0-1.04.2-1.43.59L10.3 9.45l-7.72 7.72c-.78.78-.78 2.05 0 2.83L4 21.41c.39.39.9.59 1.41.59.51 0 1.02-.2 1.41-.59l7.78-7.78 2.81-2.81c.8-.78.8-2.07 0-2.86zM5.41 20L4 18.59l7.72-7.72 1.47 1.35L5.41 20z"/>
</svg>
</button>

  <style>
    .colab-df-container {
      display:flex;
      flex-wrap:wrap;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

      <script>
        const buttonEl =
          document.querySelector('#df-841d0f9a-7f16-43b2-aff5-f0b44d8f9adc button.colab-df-convert');
        buttonEl.style.display =
          google.colab.kernel.accessAllowed ? 'block' : 'none';

        async function convertToInteractive(key) {
          const element = document.querySelector('#df-841d0f9a-7f16-43b2-aff5-f0b44d8f9adc');
          const dataTable =
            await google.colab.kernel.invokeFunction('convertToInteractive',
                                                     [key], {});
          if (!dataTable) return;

          const docLinkHtml = 'Like what you see? Visit the ' +
            '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
            + ' to learn more about interactive tables.';
          element.innerHTML = '';
          dataTable['output_type'] = 'display_data';
          await google.colab.output.renderOutput(dataTable, element);
          const docLink = document.createElement('div');
          docLink.innerHTML = docLinkHtml;
          element.appendChild(docLink);
        }
      </script>
    </div>

  </div>

```python
import seaborn as sns
import matplotlib.pyplot as plt

# Crear la gráfica
plt.figure(figsize=(15,8))
plt.title('Top 4 Países con más Empresas en Tecnología y Telecomunicaciones', fontsize=20)
plt.pie(top_4_paises_tech['+ Empresas'], labels=top_4_paises_tech.index, autopct='%1.1f%%', startangle=90, colors=sns.color_palette('Blues_d'))
plt.axis('equal')
plt.legend(loc='best', fontsize=14)
plt.tight_layout()
plt.show();
```

![png](Data_Insider_files/Data_Insider_69_0.png)

###C.¿Cuál fue el margen de pérdida de las 5 empresas que presentaron mayores perjuicios considerando el total de pérdidas registradas en la Industria de los Hoteles, Restaurantes y entretenimiento?

```python
# Filtrar el DataFrame original por Empresa, Industria, Ingresos y Ganancias
df_filtered = df_2022[['Empresa', 'Industria', 'Ingresos', 'Ganancias', 'Activos']]

# Filtrar el DataFrame por Industria = hotels, restaurants & leisure
df_hotels = df_filtered[df_filtered['Industria'] == 'hotels, restaurants & leisure']

# Agrupar el DataFrame por Empresa y sumar los Ingresos y las Ganancias por empresa
df_hotels_grouped = df_hotels.groupby('Empresa').agg({'Ingresos': 'sum', 'Ganancias': 'sum', 'Activos': 'sum'})

# Agrupar por industria y empresa, y calcular las pérdidas
df_hotels_grouped['Costos'] = df_hotels_grouped['Activos'] - df_hotels_grouped['Ganancias']
df_hotels_grouped['Perdida = Costos - Ingresos'] = df_hotels_grouped['Costos'] - df_hotels_grouped['Ingresos']

# Calcular el margen de pérdida por empresa y ordenar de mayor a menor
df_hotels_grouped['Margen de Perdida = Costos / Ingresos'] = ((df_hotels_grouped['Costos']) / df_hotels_grouped['Ingresos']) * 100
df_hotels_grouped['Margen de Perdida = Costos / Ingresos'] = df_hotels_grouped['Margen de Perdida = Costos / Ingresos'].round(1)
df_mayores_perdidas_a = df_hotels_grouped.sort_values(by=['Perdida = Costos - Ingresos', 'Margen de Perdida = Costos / Ingresos'], ascending=[True, False])

# Filtrar el DataFrame por pérdidas negativas y mostrar solo las 10 primeras empresas
df_hotels_top5 = df_mayores_perdidas_a.loc[df_mayores_perdidas_a['Perdida = Costos - Ingresos'] < 0].head(5)

# Mostrar el DataFrame con Empresa, Ingresos, Ganancias, Costos, Perdida y Margen de Pérdida
df_hotels_top5 = df_hotels_top5[['Ingresos', 'Ganancias', 'Activos', 'Costos', 'Perdida = Costos - Ingresos', 'Margen de Perdida = Costos / Ingresos']]

df_hotels_top5
```

  <div id="df-f2ea5d39-c259-4f0a-a045-9fe50b498efb">
    <div class="colab-df-container">
      <div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }

</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Ingresos</th>
      <th>Ganancias</th>
      <th>Activos</th>
      <th>Costos</th>
      <th>Perdida = Costos - Ingresos</th>
      <th>Margen de Perdida = Costos / Ingresos</th>
    </tr>
    <tr>
      <th>Empresa</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>starbucks</th>
      <td>30358.0</td>
      <td>4393.1</td>
      <td>28834.0</td>
      <td>24440.9</td>
      <td>-5917.1</td>
      <td>80.5</td>
    </tr>
  </tbody>
</table>
</div>
      <button class="colab-df-convert" onclick="convertToInteractive('df-f2ea5d39-c259-4f0a-a045-9fe50b498efb')"
              title="Convert this dataframe to an interactive table."
              style="display:none;">

<svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
width="24px">
<path d="M0 0h24v24H0V0z" fill="none"/>
<path d="M18.56 5.44l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94zm-11 1L8.5 8.5l.94-2.06 2.06-.94-2.06-.94L8.5 2.5l-.94 2.06-2.06.94zm10 10l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94z"/><path d="M17.41 7.96l-1.37-1.37c-.4-.4-.92-.59-1.43-.59-.52 0-1.04.2-1.43.59L10.3 9.45l-7.72 7.72c-.78.78-.78 2.05 0 2.83L4 21.41c.39.39.9.59 1.41.59.51 0 1.02-.2 1.41-.59l7.78-7.78 2.81-2.81c.8-.78.8-2.07 0-2.86zM5.41 20L4 18.59l7.72-7.72 1.47 1.35L5.41 20z"/>
</svg>
</button>

  <style>
    .colab-df-container {
      display:flex;
      flex-wrap:wrap;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

      <script>
        const buttonEl =
          document.querySelector('#df-f2ea5d39-c259-4f0a-a045-9fe50b498efb button.colab-df-convert');
        buttonEl.style.display =
          google.colab.kernel.accessAllowed ? 'block' : 'none';

        async function convertToInteractive(key) {
          const element = document.querySelector('#df-f2ea5d39-c259-4f0a-a045-9fe50b498efb');
          const dataTable =
            await google.colab.kernel.invokeFunction('convertToInteractive',
                                                     [key], {});
          if (!dataTable) return;

          const docLinkHtml = 'Like what you see? Visit the ' +
            '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
            + ' to learn more about interactive tables.';
          element.innerHTML = '';
          dataTable['output_type'] = 'display_data';
          await google.colab.output.renderOutput(dataTable, element);
          const docLink = document.createElement('div');
          docLink.innerHTML = docLinkHtml;
          element.appendChild(docLink);
        }
      </script>
    </div>

  </div>

```python
# Crear el gráfico de barras horizontal
plt.figure(figsize=(15, 8))

sns.set_style('whitegrid')

sns.barplot(x='Ingresos', y='Empresa', data=df_hotels_top5.reset_index(), color='orange', label='Ingresos')
sns.barplot(x='Costos', y='Empresa', data=df_hotels_top5.reset_index(), color='blue', label='Costos')
sns.barplot(x='Perdida = Costos - Ingresos', y='Empresa', data=df_hotels_top5.reset_index(), color='red', label='Pérdidas')
sns.barplot(x='Margen de Perdida = Costos / Ingresos', y='Empresa', data=df_hotels_top5.reset_index(), color='purple', label='Margen de Pérdida')

plt.title('Top 5 empresas con mayores pérdidas en la industria de hoteles, restaurantes y entretenimiento')
plt.xlabel('Monto')
plt.ylabel('Empresa')

# Mover leyenda a la parte superior del gráfico
plt.legend(fontsize=12, bbox_to_anchor=(0.5, 1.15), ncol=4)

# Agregar valores de margen de pérdida encima de cada barra
for i in range(len(df_hotels_top5)):
    margen = df_hotels_top5['Margen de Perdida = Costos / Ingresos'][i]
    plt.text(df_hotels_top5['Costos'][i] + 1, i,
             str(margen) + '%', fontsize=12, color='white', backgroundcolor='purple')
    plt.axhspan(i - 0.4, i + 0.4, facecolor='purple', alpha=0.2)

plt.show()
```

![png](Data_Insider_files/Data_Insider_72_0.png)

###D.Considerando a la Industria Petrolera en Asia, ¿Cuál o cuáles empresas superaron en más del 20% su margen de rentabilidad?

```python
import pandas as pd

# Filtrar DataFrame por la industria "oil & gas operations" y el continente "Asia" sin incluir los países de Europa
df_petroleo_asia = df_2022[(df_2022['Industria'] == 'oil & gas operations') & (df_2022['Continente'].isin(['Asia'])) & (~df_2022['Continente'].isin(['Europe']))]

# Agrupar el DataFrame por Empresa y sumar los Ingresos y las Ganancias por empresa
df_petroleo_asia_grouped = df_petroleo_asia.groupby('Empresa').agg({'Margen de Rentabilidad': 'sum', 'Activos': 'sum'})
petrolera_asia_a = df_petroleo_asia_grouped.sort_values(by=['Margen de Rentabilidad', 'Activos'], ascending=[False, False])

empresas_mayor_20 = petrolera_asia_a[petrolera_asia_a['Margen de Rentabilidad'] >= 0.2]

# Agregar columnas de País y Continente
empresas_mayor_20 = pd.merge(empresas_mayor_20, df_2022[['Empresa', 'Pais', 'Continente']], on='Empresa').drop_duplicates()

# Seleccionar columnas de interés
empresas_mayor_20 = empresas_mayor_20[['Empresa', 'Pais', 'Continente', 'Activos', 'Margen de Rentabilidad']]

empresas_mayor_20
```

  <div id="df-d4f48f16-2814-4390-9a4a-54abce27f8b9">
    <div class="colab-df-container">
      <div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }

</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Empresa</th>
      <th>Pais</th>
      <th>Continente</th>
      <th>Activos</th>
      <th>Margen de Rentabilidad</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>gazprom</td>
      <td>Russia</td>
      <td>Asia</td>
      <td>360474.0</td>
      <td>0.216852</td>
    </tr>
  </tbody>
</table>
</div>
      <button class="colab-df-convert" onclick="convertToInteractive('df-d4f48f16-2814-4390-9a4a-54abce27f8b9')"
              title="Convert this dataframe to an interactive table."
              style="display:none;">

<svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
width="24px">
<path d="M0 0h24v24H0V0z" fill="none"/>
<path d="M18.56 5.44l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94zm-11 1L8.5 8.5l.94-2.06 2.06-.94-2.06-.94L8.5 2.5l-.94 2.06-2.06.94zm10 10l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94z"/><path d="M17.41 7.96l-1.37-1.37c-.4-.4-.92-.59-1.43-.59-.52 0-1.04.2-1.43.59L10.3 9.45l-7.72 7.72c-.78.78-.78 2.05 0 2.83L4 21.41c.39.39.9.59 1.41.59.51 0 1.02-.2 1.41-.59l7.78-7.78 2.81-2.81c.8-.78.8-2.07 0-2.86zM5.41 20L4 18.59l7.72-7.72 1.47 1.35L5.41 20z"/>
</svg>
</button>

  <style>
    .colab-df-container {
      display:flex;
      flex-wrap:wrap;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

      <script>
        const buttonEl =
          document.querySelector('#df-d4f48f16-2814-4390-9a4a-54abce27f8b9 button.colab-df-convert');
        buttonEl.style.display =
          google.colab.kernel.accessAllowed ? 'block' : 'none';

        async function convertToInteractive(key) {
          const element = document.querySelector('#df-d4f48f16-2814-4390-9a4a-54abce27f8b9');
          const dataTable =
            await google.colab.kernel.invokeFunction('convertToInteractive',
                                                     [key], {});
          if (!dataTable) return;

          const docLinkHtml = 'Like what you see? Visit the ' +
            '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
            + ' to learn more about interactive tables.';
          element.innerHTML = '';
          dataTable['output_type'] = 'display_data';
          await google.colab.output.renderOutput(dataTable, element);
          const docLink = document.createElement('div');
          docLink.innerHTML = docLinkHtml;
          element.appendChild(docLink);
        }
      </script>
    </div>

  </div>

```python
import pandas as pd
import matplotlib.pyplot as plt
import matplotlib.ticker as mtick
import seaborn as sns

# Filtrar DataFrame por la industria "oil & gas operations" y el continente "Asia" sin incluir los países de Europa
df_petroleo_asia = df_2022[(df_2022['Industria'] == 'oil & gas operations') & (df_2022['Continente'].isin(['Asia'])) & (~df_2022['Continente'].isin(['Europe']))]

# Agrupar el DataFrame por Empresa y sumar los Ingresos y las Ganancias por empresa
df_petroleo_asia_grouped = df_petroleo_asia.groupby('Empresa').agg({'Margen de Rentabilidad': 'sum', 'Activos': 'sum'})
petrolera_asia_a = df_petroleo_asia_grouped.sort_values(by=['Margen de Rentabilidad', 'Activos'], ascending=[False, False])

# Filtrar empresas con margen de rentabilidad mayor al 20%
empresas_mayor_20 = petrolera_asia_a[petrolera_asia_a['Margen de Rentabilidad'] > 0.2]

# Filtrar empresas con margen de rentabilidad menor o igual al 20%
empresas_no_mayor_20 = petrolera_asia_a[petrolera_asia_a['Margen de Rentabilidad'] <= 0.2]

# Agregar columna de País utilizando la función merge y la columna 'Codigo_Pais'
empresas_mayor_20 = pd.merge(empresas_mayor_20, df_2022[['Empresa', 'Pais']], on='Empresa').drop_duplicates()
empresas_no_mayor_20 = pd.merge(empresas_no_mayor_20, df_2022[['Empresa', 'Pais']], on='Empresa').drop_duplicates()

# Seleccionar columnas de interés
empresas_mayor_20 = empresas_mayor_20[['Empresa', 'Activos', 'Margen de Rentabilidad', 'Pais']]
empresas_no_mayor_20 = empresas_no_mayor_20[['Empresa', 'Activos', 'Margen de Rentabilidad', 'Pais']]

# Crear el gráfico personalizado
plt.figure(figsize=(15, 8))

sns.set_style('darkgrid')

# Crear scatterplot con empresas con margen de rentabilidad en el eje x y activos en el eje y
sns.scatterplot(data=empresas_mayor_20, x='Margen de Rentabilidad', y='Activos', hue='Empresa', alpha=0.7, palette='bright', marker='^', s=200)

sns.scatterplot(data=empresas_no_mayor_20, x='Margen de Rentabilidad', y='Activos', hue='Empresa', alpha=0.7, palette='bright', marker='o', s=200)

# Convertir margen de rentabilidad a porcentaje
plt.gca().xaxis.set_major_formatter(mtick.PercentFormatter(xmax=1, decimals=0))

# Establecer título, subtítulo, nombres de los ejes y leyenda
plt.title('Empresas petroleras en Asia con margen de rentabilidad superior al 20%')
plt.suptitle('Relación entre margen de rentabilidad, empresa y activos', fontsize=14, y=0.95)
plt.xlabel('Margen de rentabilidad')
plt.ylabel('Activos (en millones)')

# Crear nueva lista de etiquetas para la leyenda
etiquetas_mayor_20 = [f"{row['Empresa']} ({row['Pais']})" for _, row in empresas_mayor_20.iterrows()]
etiquetas_no_mayor_20 = [f"{row['Empresa']} ({row['Pais']})" for _, row in empresas_no_mayor_20.iterrows()]

# Combinar lista de etiquetas para la leyenda
etiquetas = etiquetas_mayor_20 + etiquetas_no_mayor_20

# Establecer leyenda con las nuevas etiquetas
plt.legend(title='Empresa (País)', fontsize=10, labels=etiquetas, markerscale=0, scatterpoints=1)

# Establecer tamaño de fuente para los ejes
plt.xticks(fontsize=10, rotation=0)
plt.yticks(fontsize=10)

# Cambiar unidades de los activos a millones y mostrar dos decimales
ax = plt.gca()
ax.set_xticklabels([f"{int(x*100)}%" for x in ax.get_xticks()])
ax.set_yticklabels([f"{round(x/1e6, 1)}M" for x in ax.get_yticks()])

# Agregar el nombre de cada empresa y su país en su respectiva posición para empresas_mayor_20
for _, row in empresas_mayor_20.iterrows():
    plt.annotate(f"{row['Empresa']} ({row['Pais']})", xy=(row['Margen de Rentabilidad'], row['Activos']), size=9, ha='center', va='center')

# Agregar el nombre de cada empresa y su país en su respectiva posición para empresas_no_mayor_20
for _, row in empresas_no_mayor_20.iterrows():
    plt.annotate(f"{row['Empresa']} ({row['Pais']})", xy=(row['Margen de Rentabilidad'], row['Activos']), size=9, ha='center', va='center')

# Mostrar gráfico
plt.show()
```

    <ipython-input-45-af2ebefaadef>:62: UserWarning: FixedFormatter should only be used together with FixedLocator
      ax.set_xticklabels([f"{int(x*100)}%" for x in ax.get_xticks()])
    <ipython-input-45-af2ebefaadef>:63: UserWarning: FixedFormatter should only be used together with FixedLocator
      ax.set_yticklabels([f"{round(x/1e6, 1)}M" for x in ax.get_yticks()])

![png](Data_Insider_files/Data_Insider_75_1.png)

###E.¿Cuáles fueron las empresas norteamericanas con el mayor porcentaje de rentabilidad por industria?

```python
import pandas as pd

# Seleccionar las empresas norteamericanas
df_norteamerica = df_2022[df_2022['Continente'] == 'North America']

# Obtener el porcentaje de rentabilidad por industria
porcentaje_rentabilidad = df_norteamerica.groupby('Industria')['Margen de Rentabilidad'].mean()

# Obtener las empresas con mayor porcentaje de rentabilidad por industria
empresas_max_rentabilidad = df_norteamerica.groupby('Industria')[['Empresa', 'Margen de Rentabilidad']].apply(lambda x: x[x['Margen de Rentabilidad'] == x['Margen de Rentabilidad'].max()])

# Eliminar el nivel 1 del índice jerárquico
empresas_max_rentabilidad = empresas_max_rentabilidad.droplevel(1)

# Combinar DataFrames para agregar la columna Industria
empresas_max_rentabilidad = pd.merge(empresas_max_rentabilidad, df_norteamerica[['Empresa', 'Industria','Ganancias','Ingresos']], on='Empresa', how='left')

# Ordenar las empresas de forma ascendente
empresas_max_rentabilidad = empresas_max_rentabilidad.sort_values(by='Margen de Rentabilidad', ascending=False)

# Seleccionar las columnas que se desean mostrar
empresas_max_rentabilidad = empresas_max_rentabilidad.loc[:, ['Industria', 'Empresa','Ganancias','Ingresos', 'Margen de Rentabilidad']]

# Mostrar el DataFrame sin la columna level_1
print(empresas_max_rentabilidad.to_string(index=False))
```

                           Industria                      Empresa  Ganancias  Ingresos  Margen de Rentabilidad
              it software & services                    microsoft    71185.0  184903.0                0.384986
              diversified financials               jpmorgan chase    42115.0  124542.0                0.338159
                             banking              bank of america    30995.0   96826.0                0.320110
               food, drink & tobacco  philip morris international     8997.0   31507.0                0.285556
                      semiconductors                     qualcomm     9986.0   36036.0                0.277112
               drugs & biotechnology                       pfizer    21979.0   81491.0                0.269711
     technology hardware & equipment                        apple   100555.0  378697.0                0.265529
        business services & supplies                   fannie mae    22176.0  100328.0                0.221035
                       conglomerates                      danaher     6456.0   30283.0                0.213189
                           materials                        nucor     7954.5   39960.0                0.199062
    health care equipment & services     thermo fisher scientific     7725.0   39211.0                0.197011
                 aerospace & defense             northrop grumman     7005.0   35667.0                0.196400
                   consumer durables             procter & gamble    14596.0   79618.0                0.183325
                           insurance american international group     9388.0   52057.0                0.180341
                oil & gas operations               conocophillips     8079.0   46056.0                0.175417
                               media                      netflix     5007.0   30402.0                0.164693
          telecommunication services       verizon communications    21520.0  134346.0                0.160183
       hotels, restaurants & leisure                    starbucks     4393.1   30358.0                0.144710
                       capital goods                  caterpillar     6489.0   50984.0                0.127275
                           chemicals                          dow     6854.0   58350.0                0.117464
                           retailing                       lowe's     8410.0   96249.0                0.087378
                      transportation                        fedex     5126.0   91548.0                0.055992
                        food markets                        metro      677.9   14612.0                0.046393
                           utilities                       exelon     1706.0   39268.0                0.043445
                   trading companies            arrow electronics     1108.2   34477.0                0.032143

```python
# import pandas as pd

# # Filtrar por la empresa ExxonMobil y sumar sus ganancias
# ganancias_exxonmobil = df_2022[df_2022['Empresa'] == 'microsoft']['Margen de Rentabilidad'].mean()

# ganancias_exxonmobil
```

```python
# Crear el gráfico de puntos con Seaborn
sns.set(rc={"figure.figsize":(15, 8)})
sns.set_palette("Paired")
fig, ax = plt.subplots(2, figsize=(15, 10), gridspec_kw={'height_ratios': [8, 2]})
sns.stripplot(x='Margen de Rentabilidad', y='Industria', data=empresas_max_rentabilidad, size=12, jitter=True, hue='Industria', palette='Set2', ax=ax[0])

# Agregar grid para guía de x y y
ax[0].grid(True)

# Configurar el título, el subtítulo, los nombres de los ejes
ax[0].set_title('Empresas con Mayor Margen de Rentabilidad por Industria en Norteamérica', fontsize=24, y=1.05)
ax[0].set_xlabel('MR = Ganancias / Ingresos', fontsize=18)
ax[0].set_ylabel('Industria', fontsize=18)

# Eliminar la leyenda que se superpone al gráfico
ax[0].get_legend().remove()

# Crear una leyenda separada para el gráfico
legend = ax[1].legend(*ax[0].get_legend_handles_labels(), loc='center', ncol=5, fontsize=14)
ax[1].axis('off')

# Mostrar el gráfico
plt.show()
```

![png](Data_Insider_files/Data_Insider_79_0.png)

###F. Excluyendo a la industria Bancaria, ¿Cuáles fueron las empresas europeas con mayores pérdidas registradas por industria a nivel global?

```python
# Filtrar por ['Empresa', 'Industria', 'Ingresos', 'Activos', 'Ganancias', Continente]
df_filt = df_2022[['Empresa', 'Industria', 'Ingresos', 'Activos', 'Ganancias', 'Continente']]

# Filtrar por ['Continente'] == 'Europe' y ['Industria'] != 'banking'
df_eur_sin_bancos = df_filt[(df_filt['Continente'] == 'Europe') & (df_filt['Industria'] != 'banking')]

# Agrupar por industria y empresa, y calcular las pérdidas
df_eur_perdidas = df_eur_sin_bancos.groupby(['Industria', 'Empresa'], as_index=False).agg({'Ingresos': 'sum', 'Activos': 'sum', 'Ganancias': 'sum'})
df_eur_perdidas['Costos'] = df_eur_perdidas['Activos'] - df_eur_perdidas['Ganancias']
df_eur_perdidas['Perdidas'] = df_eur_perdidas['Costos'] - df_eur_perdidas['Ingresos']

# Encontrar la empresa con la mayor pérdida por industria
df_max_perdida = df_eur_perdidas[df_eur_perdidas['Perdidas'] < 0].groupby('Industria', as_index=False).apply(lambda x: x.loc[x['Perdidas'].idxmax()])

# Cambiar el nombre de las columnas 'Costos' y 'Perdidas'
df_max_perdida = df_max_perdida.rename(columns={'Costos': 'Costos = Activos - Ganancias', 'Perdidas': 'Perdidas = Costos - Ingresos'})

# Mostrar el DataFrame con la empresa con la mayor pérdida por industria
df_max_perdida = df_max_perdida[['Industria', 'Empresa', 'Ingresos', 'Activos', 'Ganancias', 'Costos = Activos - Ganancias', 'Perdidas = Costos - Ingresos']]
df_max_perdida = df_max_perdida.sort_values('Perdidas = Costos - Ingresos', ascending=True)

df_max_perdida
```

  <div id="df-8e6020aa-840b-4ba6-a399-81213a97798d">
    <div class="colab-df-container">
      <div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }

</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Industria</th>
      <th>Empresa</th>
      <th>Ingresos</th>
      <th>Activos</th>
      <th>Ganancias</th>
      <th>Costos = Activos - Ganancias</th>
      <th>Perdidas = Costos - Ingresos</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1</th>
      <td>food markets</td>
      <td>tesco</td>
      <td>84168.0</td>
      <td>66217.0</td>
      <td>2063.6</td>
      <td>64153.4</td>
      <td>-20014.6</td>
    </tr>
    <tr>
      <th>2</th>
      <td>it software &amp; services</td>
      <td>accenture</td>
      <td>56695.0</td>
      <td>44318.0</td>
      <td>6391.6</td>
      <td>37926.4</td>
      <td>-18768.6</td>
    </tr>
    <tr>
      <th>0</th>
      <td>chemicals</td>
      <td>lyondellbasell industries</td>
      <td>46153.0</td>
      <td>36742.0</td>
      <td>5603.0</td>
      <td>31139.0</td>
      <td>-15014.0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>retailing</td>
      <td>inditex</td>
      <td>32572.0</td>
      <td>32447.0</td>
      <td>3811.2</td>
      <td>28635.8</td>
      <td>-3936.2</td>
    </tr>
    <tr>
      <th>3</th>
      <td>materials</td>
      <td>arcelormittal</td>
      <td>76654.0</td>
      <td>90512.0</td>
      <td>14985.4</td>
      <td>75526.6</td>
      <td>-1127.4</td>
    </tr>
  </tbody>
</table>
</div>
      <button class="colab-df-convert" onclick="convertToInteractive('df-8e6020aa-840b-4ba6-a399-81213a97798d')"
              title="Convert this dataframe to an interactive table."
              style="display:none;">

<svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
width="24px">
<path d="M0 0h24v24H0V0z" fill="none"/>
<path d="M18.56 5.44l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94zm-11 1L8.5 8.5l.94-2.06 2.06-.94-2.06-.94L8.5 2.5l-.94 2.06-2.06.94zm10 10l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94z"/><path d="M17.41 7.96l-1.37-1.37c-.4-.4-.92-.59-1.43-.59-.52 0-1.04.2-1.43.59L10.3 9.45l-7.72 7.72c-.78.78-.78 2.05 0 2.83L4 21.41c.39.39.9.59 1.41.59.51 0 1.02-.2 1.41-.59l7.78-7.78 2.81-2.81c.8-.78.8-2.07 0-2.86zM5.41 20L4 18.59l7.72-7.72 1.47 1.35L5.41 20z"/>
</svg>
</button>

  <style>
    .colab-df-container {
      display:flex;
      flex-wrap:wrap;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

      <script>
        const buttonEl =
          document.querySelector('#df-8e6020aa-840b-4ba6-a399-81213a97798d button.colab-df-convert');
        buttonEl.style.display =
          google.colab.kernel.accessAllowed ? 'block' : 'none';

        async function convertToInteractive(key) {
          const element = document.querySelector('#df-8e6020aa-840b-4ba6-a399-81213a97798d');
          const dataTable =
            await google.colab.kernel.invokeFunction('convertToInteractive',
                                                     [key], {});
          if (!dataTable) return;

          const docLinkHtml = 'Like what you see? Visit the ' +
            '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
            + ' to learn more about interactive tables.';
          element.innerHTML = '';
          dataTable['output_type'] = 'display_data';
          await google.colab.output.renderOutput(dataTable, element);
          const docLink = document.createElement('div');
          docLink.innerHTML = docLinkHtml;
          element.appendChild(docLink);
        }
      </script>
    </div>

  </div>

```python
import seaborn as sns
import matplotlib.pyplot as plt

# Filtrar por ['Empresa', 'Industria', 'Ingresos', 'Activos', 'Ganancias', Continente]
df_filt = df_2022[['Empresa', 'Industria', 'Ingresos', 'Activos', 'Ganancias', 'Continente']]

# Filtrar por ['Continente'] == 'Europe' y ['Industria'] != 'banking'
df_eur_sin_bancos = df_filt[(df_filt['Continente'] == 'Europe') & (df_filt['Industria'] != 'banking')]

# Agrupar por industria y empresa, y calcular las pérdidas
df_eur_perdidas = df_eur_sin_bancos.groupby(['Industria', 'Empresa'], as_index=False).agg({'Ingresos': 'sum', 'Activos': 'sum', 'Ganancias': 'sum'})
df_eur_perdidas['Costos'] = df_eur_perdidas['Activos'] - df_eur_perdidas['Ganancias']
df_eur_perdidas['Perdidas'] = df_eur_perdidas['Costos'] - df_eur_perdidas['Ingresos']

# Encontrar la empresa con la mayor pérdida por industria
df_max_perdida = df_eur_perdidas[df_eur_perdidas['Perdidas'] < 0].groupby('Industria', as_index=False).apply(lambda x: x.loc[x['Perdidas'].idxmax()])

# Cambiar el nombre de las columnas 'Costos' y 'Perdidas'
df_max_perdida = df_max_perdida.rename(columns={'Costos': 'Costos = Activos - Ganancias', 'Perdidas': 'Perdidas = Costos - Ingresos'})

# Mostrar el DataFrame con la empresa con la mayor pérdida por industria
df_max_perdida = df_max_perdida[['Industria', 'Empresa', 'Ingresos', 'Activos', 'Ganancias', 'Costos = Activos - Ganancias', 'Perdidas = Costos - Ingresos']]
df_max_perdida = df_max_perdida.sort_values('Perdidas = Costos - Ingresos', ascending=True)

# Crear el gráfico de barras horizontales apiladas con Seaborn
sns.set(rc={"figure.figsize":(15, 8)})
sns.set_palette("husl")
fig, ax = plt.subplots()
sns.barplot(x='Perdidas = Costos - Ingresos', y='Industria', hue='Empresa', data=df_max_perdida, dodge=False, orient='h')

# Configurar el título, el subtítulo, los nombres de los ejes, la leyenda y el tamaño de fuente
ax.set_title('Empresas con Mayores Pérdidas por Industria en Europa (sin bancos)', fontsize=24, y=1.05)
ax.set_xlabel('Perdidas = Costos - Ingresos', fontsize=18)
ax.set_ylabel('Industria', fontsize=18)
ax.legend(loc='center left', bbox_to_anchor=(1, 0.5), fontsize=14)
plt.xticks(fontsize=14)
plt.yticks(fontsize=14)

# Mostrar el gráfico
plt.show()
```

![png](Data_Insider_files/Data_Insider_82_0.png)

###G. ¿Cuál fue la distribución de Ingresos y Activos con respecto a las ganancias de los bancos cuyos activos no superan los 30000 millones de dólares?

```python
# Filtrar solo las columnas necesarias
df_bancos_activos = df_2022[['Empresa', 'Industria', 'Ingresos', 'Activos', 'Ganancias', 'Margen de Rentabilidad', 'Rentabilidad de los Activos (ROA)']]

# Filtrar solo la industria Banking
df_bancos_activos = df_bancos_activos[df_bancos_activos['Industria'] == 'banking']

# Agrupar por empresa e industria y sumar los 'Ingresos', 'Activos', 'Ganancias'
#df_bancos_activos = df_bancos_activos.groupby(['Empresa', 'Industria'])[['Ingresos', 'Activos', 'Ganancias']].sum().reset_index()

# Agrupar por empresa y calcular el promedio de los 'Margen de Rentabilidad' y 'Rentabilidad de los Activos (ROA)'
df_bancos_activos = df_bancos_activos.groupby('Empresa').agg({
    'Ingresos': 'sum',
    'Activos': 'sum',
    'Ganancias': 'sum',
    'Margen de Rentabilidad': 'mean',
    'Rentabilidad de los Activos (ROA)': 'mean'
}).reset_index()

# Filtrar por empresas cuyos activos no superan los 30000 millones de dólares
df_bancos_activos = df_bancos_activos[df_bancos_activos['Activos'] <= 30000]

# Ordenar el DataFrame por margen de rentabilidad y rentabilidad de los activos (ROA)
df_bancos_activos = df_bancos_activos.sort_values(by=['Rentabilidad de los Activos (ROA)','Margen de Rentabilidad'], ascending=[False, False])

# Seleccionar las columnas de interés
df_bancos_activos = df_bancos_activos[['Empresa', 'Ingresos', 'Activos', 'Ganancias', 'Margen de Rentabilidad', 'Rentabilidad de los Activos (ROA)']]

# Mostrar el DataFrame resultante
df_bancos_activos
```

  <div id="df-59415ba6-a857-4171-939f-02c197a8a0aa">
    <div class="colab-df-container">
      <div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }

</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Empresa</th>
      <th>Ingresos</th>
      <th>Activos</th>
      <th>Ganancias</th>
      <th>Margen de Rentabilidad</th>
      <th>Rentabilidad de los Activos (ROA)</th>
    </tr>
  </thead>
  <tbody>
  </tbody>
</table>
</div>
      <button class="colab-df-convert" onclick="convertToInteractive('df-59415ba6-a857-4171-939f-02c197a8a0aa')"
              title="Convert this dataframe to an interactive table."
              style="display:none;">

<svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
width="24px">
<path d="M0 0h24v24H0V0z" fill="none"/>
<path d="M18.56 5.44l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94zm-11 1L8.5 8.5l.94-2.06 2.06-.94-2.06-.94L8.5 2.5l-.94 2.06-2.06.94zm10 10l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94z"/><path d="M17.41 7.96l-1.37-1.37c-.4-.4-.92-.59-1.43-.59-.52 0-1.04.2-1.43.59L10.3 9.45l-7.72 7.72c-.78.78-.78 2.05 0 2.83L4 21.41c.39.39.9.59 1.41.59.51 0 1.02-.2 1.41-.59l7.78-7.78 2.81-2.81c.8-.78.8-2.07 0-2.86zM5.41 20L4 18.59l7.72-7.72 1.47 1.35L5.41 20z"/>
</svg>
</button>

  <style>
    .colab-df-container {
      display:flex;
      flex-wrap:wrap;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

      <script>
        const buttonEl =
          document.querySelector('#df-59415ba6-a857-4171-939f-02c197a8a0aa button.colab-df-convert');
        buttonEl.style.display =
          google.colab.kernel.accessAllowed ? 'block' : 'none';

        async function convertToInteractive(key) {
          const element = document.querySelector('#df-59415ba6-a857-4171-939f-02c197a8a0aa');
          const dataTable =
            await google.colab.kernel.invokeFunction('convertToInteractive',
                                                     [key], {});
          if (!dataTable) return;

          const docLinkHtml = 'Like what you see? Visit the ' +
            '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
            + ' to learn more about interactive tables.';
          element.innerHTML = '';
          dataTable['output_type'] = 'display_data';
          await google.colab.output.renderOutput(dataTable, element);
          const docLink = document.createElement('div');
          docLink.innerHTML = docLinkHtml;
          element.appendChild(docLink);
        }
      </script>
    </div>

  </div>

```python
import seaborn as sns
import matplotlib.pyplot as plt

# Filtrar solo las columnas necesarias
df_bancos_activos = df_2022[['Empresa', 'Industria', 'Ingresos', 'Activos', 'Ganancias', 'Margen de Rentabilidad', 'Rentabilidad de los Activos (ROA)']]

# Filtrar solo la industria Banking
df_bancos_activos = df_bancos_activos[df_bancos_activos['Industria'] == 'banking']

# Agrupar por empresa y calcular el promedio de los 'Margen de Rentabilidad' y 'Rentabilidad de los Activos (ROA)'
df_bancos_activos = df_bancos_activos.groupby('Empresa').agg({
    'Ingresos': 'sum',
    'Activos': 'sum',
    'Ganancias': 'sum',
    'Margen de Rentabilidad': 'mean',
    'Rentabilidad de los Activos (ROA)': 'mean'
}).reset_index()

# Ordenar el DataFrame por margen de rentabilidad y rentabilidad de los activos (ROA)
df_bancos_activos = df_bancos_activos.sort_values(by=['Rentabilidad de los Activos (ROA)','Margen de Rentabilidad'], ascending=[False, False])

# Seleccionar las columnas de interés
df_bancos_activos = df_bancos_activos[['Empresa', 'Ingresos', 'Activos', 'Ganancias', 'Margen de Rentabilidad', 'Rentabilidad de los Activos (ROA)']]

# Convertir los activos a millones de dólares
df_bancos_activos['Activos (Millones de dólares)'] = df_bancos_activos['Activos'] / 1000

# Convertir el margen de rentabilidad a porcentaje
df_bancos_activos['Margen de Rentabilidad %'] = df_bancos_activos['Margen de Rentabilidad'] * 100

# Crear un heatmap utilizando Seaborn
plt.figure(figsize=(15, 8))
ax = sns.heatmap(data=df_bancos_activos.pivot(index='Empresa', columns='Rentabilidad de los Activos (ROA)', values='Activos (Millones de dólares)'), cmap='coolwarm', annot=df_bancos_activos.pivot(index='Empresa', columns='Rentabilidad de los Activos (ROA)', values='Margen de Rentabilidad').applymap(lambda x: '{:.1f}%'.format(x*100)), fmt='', annot_kws={'fontsize': 10})

# Establecer los títulos y nombres de los ejes
plt.title('Relación entre margen de rentabilidad, rentabilidad de los activos y activos (Millones de dólares) para empresas de la industria bancaria')
plt.xlabel('Rentabilidad de los Activos (ROA) (%)')
plt.ylabel('Empresa')

# Modificar los ticks de los ejes para que muestren los valores en porcentaje y millones de dólares
xticklabels = ax.get_xticklabels()
new_xticklabels = ['{:.1f}%'.format(float(label.get_text())*100) for label in xticklabels]
ax.set_xticklabels(new_xticklabels, fontsize=10)

# Mostrar el gráfico
plt.show()
```

![png](Data_Insider_files/Data_Insider_85_0.png)

###H. Considerando el histórico de valores de las acciones en el año 2022 de las 5 empresas de tu elección (Paso 2), Indica ¿Cuál fue la mejor semana para comprar y cuál para vender respectivamente? (Se compra cuando el precio es bajo, y se vende cuando el precio es alto)

```python
import pandas as pd

AAPL = pd.read_csv('/content/drive/MyDrive/BootCamp/CHALLENGE/Spring_2/EmpresasValores/AAPL.csv')
GOOG = pd.read_csv('/content/drive/MyDrive/BootCamp/CHALLENGE/Spring_2/EmpresasValores/GOOG.csv')
MSFT = pd.read_csv('/content/drive/MyDrive/BootCamp/CHALLENGE/Spring_2/EmpresasValores/MSFT.csv')
TSLA = pd.read_csv('/content/drive/MyDrive/BootCamp/CHALLENGE/Spring_2/EmpresasValores/TSLA.csv')
AMZN = pd.read_csv('/content/drive/MyDrive/BootCamp/CHALLENGE/Spring_2/EmpresasValores/AMZN.csv')
```

```python
AAPL.dtypes
```

    v     float64
    vw    float64
    o     float64
    c     float64
    h     float64
    l     float64
    t       int64
    n       int64
    dtype: object

```python
AAPL['date'] = pd.to_datetime(AAPL['t'], unit='ms')
AAPL.set_index('date', inplace=True)

GOOG['date'] = pd.to_datetime(GOOG['t'], unit='ms')
GOOG.set_index('date', inplace=True)

MSFT['date'] = pd.to_datetime(MSFT['t'], unit='ms')
MSFT.set_index('date', inplace=True)

TSLA['date'] = pd.to_datetime(TSLA['t'], unit='ms')
TSLA.set_index('date', inplace=True)

AMZN['date'] = pd.to_datetime(AMZN['t'], unit='ms')
AMZN.set_index('date', inplace=True)
```

```python
AAPL_weekly = AAPL.resample('W')['c'].mean()
GOOG_weekly = GOOG.resample('W')['c'].mean()
MSFT_weekly = MSFT.resample('W')['c'].mean()
TSLA_weekly = TSLA.resample('W')['c'].mean()
AMZN_weekly = AMZN.resample('W')['c'].mean()
```

```python
AAPL_mejor_semana_compra = AAPL_weekly.idxmin().strftime('%Y-%m-%d')
AAPL_mejor_semana_venta = AAPL_weekly.idxmax().strftime('%Y-%m-%d')

GOOG_mejor_semana_compra = GOOG_weekly.idxmin().strftime('%Y-%m-%d')
GOOG_mejor_semana_venta = GOOG_weekly.idxmax().strftime('%Y-%m-%d')

MSFT_mejor_semana_compra = MSFT_weekly.idxmin().strftime('%Y-%m-%d')
MSFT_mejor_semana_venta = MSFT_weekly.idxmax().strftime('%Y-%m-%d')

TSLA_mejor_semana_compra = TSLA_weekly.idxmin().strftime('%Y-%m-%d')
TSLA_mejor_semana_venta = TSLA_weekly.idxmax().strftime('%Y-%m-%d')

AMZN_mejor_semana_compra = AMZN_weekly.idxmin().strftime('%Y-%m-%d')
AMZN_mejor_semana_venta = AMZN_weekly.idxmax().strftime('%Y-%m-%d')
```

```python
print('La mejor semana para comprar acciones de Apple en el año 2022 es:    ', AAPL_mejor_semana_compra)
print('La mejor semana para vender acciones de Apple en el año 2022 es:     ', AAPL_mejor_semana_venta)

print('')

print('La mejor semana para comprar acciones de Google en el año 2022 es:    ', GOOG_mejor_semana_compra)
print('La mejor semana para vender acciones de Google en el año 2022 es:     ', GOOG_mejor_semana_venta)

print('')

print('La mejor semana para comprar acciones de Microsoft en el año 2022 es:    ', MSFT_mejor_semana_compra)
print('La mejor semana para vender acciones de Microsoft en el año 2022 es:     ', MSFT_mejor_semana_venta)

print('')

print('La mejor semana para comprar acciones de Tesla en el año 2022 es:    ', TSLA_mejor_semana_compra)
print('La mejor semana para vender acciones de Tesla en el año 2022 es:     ', TSLA_mejor_semana_venta)

print('')

print('La mejor semana para comprar acciones de Amazon en el año 2022 es:    ', AMZN_mejor_semana_compra)
print('La mejor semana para vender acciones de Amazon en el año 2022 es:     ', AMZN_mejor_semana_venta)
```

    La mejor semana para comprar acciones de Apple en el año 2022 es:     2023-01-01
    La mejor semana para vender acciones de Apple en el año 2022 es:      2022-04-03

    La mejor semana para comprar acciones de Google en el año 2022 es:     2023-01-01
    La mejor semana para vender acciones de Google en el año 2022 es:      2022-04-03

    La mejor semana para comprar acciones de Microsoft en el año 2022 es:     2022-11-06
    La mejor semana para vender acciones de Microsoft en el año 2022 es:      2022-01-09

    La mejor semana para comprar acciones de Tesla en el año 2022 es:     2023-01-01
    La mejor semana para vender acciones de Tesla en el año 2022 es:      2022-01-09

    La mejor semana para comprar acciones de Amazon en el año 2022 es:     2023-01-01
    La mejor semana para vender acciones de Amazon en el año 2022 es:      2022-04-03

```python
import matplotlib.pyplot as plt
import seaborn as sns

# Obtener las fechas de la mejor semana de compra y venta para cada acción
AAPL_mejor_semana_compra = AAPL_weekly.idxmin()
AAPL_mejor_semana_venta = AAPL_weekly.idxmax()
GOOG_mejor_semana_compra = GOOG_weekly.idxmin()
GOOG_mejor_semana_venta = GOOG_weekly.idxmax()
MSFT_mejor_semana_compra = MSFT_weekly.idxmin()
MSFT_mejor_semana_venta = MSFT_weekly.idxmax()
TSLA_mejor_semana_compra = TSLA_weekly.idxmin()
TSLA_mejor_semana_venta = TSLA_weekly.idxmax()
AMZN_mejor_semana_compra = AMZN_weekly.idxmin()
AMZN_mejor_semana_venta = AMZN_weekly.idxmax()

# Crear una figura y un eje con un subplot
fig, ax = plt.subplots(figsize=(18, 10))

# Graficar la serie de tiempo de precios de cierre semanales para cada acción
ax.plot(AAPL_weekly.index, AAPL_weekly, label='AAPL')
ax.plot(GOOG_weekly.index, GOOG_weekly, label='GOOG')
ax.plot(MSFT_weekly.index, MSFT_weekly, label='MSFT')
ax.plot(TSLA_weekly.index, TSLA_weekly, label='TSLA')
ax.plot(AMZN_weekly.index, AMZN_weekly, label='AMZN')

# Graficar los triángulos de compra y de venta para cada acción
ax.scatter(AAPL_mejor_semana_compra, AAPL_weekly.loc[AAPL_mejor_semana_compra], marker='^', color='green', s=150, label='Semana de compra')
ax.scatter(AAPL_mejor_semana_venta, AAPL_weekly.loc[AAPL_mejor_semana_venta], marker='^', color='red', s=150, label='Semana de venta')
ax.scatter(GOOG_mejor_semana_compra, GOOG_weekly.loc[GOOG_mejor_semana_compra], marker='^', color='green', s=150)
ax.scatter(GOOG_mejor_semana_venta, GOOG_weekly.loc[GOOG_mejor_semana_venta], marker='^', color='red', s=150)
ax.scatter(MSFT_mejor_semana_compra, MSFT_weekly.loc[MSFT_mejor_semana_compra], marker='^', color='green', s=150)
ax.scatter(MSFT_mejor_semana_venta, MSFT_weekly.loc[MSFT_mejor_semana_venta], marker='^', color='red', s=150)
ax.scatter(TSLA_mejor_semana_compra, TSLA_weekly.loc[TSLA_mejor_semana_compra], marker='^', color='green', s=150)
ax.scatter(TSLA_mejor_semana_venta, TSLA_weekly.loc[TSLA_mejor_semana_venta], marker='^', color='red', s=150)
ax.scatter(AMZN_mejor_semana_compra, AMZN_weekly.loc[AMZN_mejor_semana_compra], marker='^', color='green', s=150)
ax.scatter(AMZN_mejor_semana_venta, AMZN_weekly.loc[AMZN_mejor_semana_venta], marker='^', color='red', s=150)

# Configurar el eje Y para no mostrar los valores
ax.set_yticks([])

# Agregar títulos y etiquetas al subplot
ax.set_title('Mejor semana para comprar y vender acciones (2022) AAPL, GOOG, MSFT, TSLA y AMZN')
#ax.set_ylabel('Precio de cierre semanal')
ax.set_xlabel('Fecha')
ax.legend()

# Mostrar el gráfico
plt.show()
```

![png](Data_Insider_files/Data_Insider_93_0.png)

##Cuestionario B

Con los resultados de tus consultas a los datos, llegó la hora de poner en práctica tus conocimientos en [Matplotlib: Visualization with Python](https://matplotlib.org/) y [seaborn: statistical data visualization](https://seaborn.pydata.org/)

Debes generar una **gráfica para cada pregunta formulada**, utilizando todo el potencial que estas herramientas de visualización ofrecen. Establece un tamaño de lienzo de 15 x 8, un título, un subtítulo, los nombres a los ejes, leyenda, tamaño de fuente, una paleta de colores que facilite la visualización y que sea de tu gusto.

Dentro de los gráficos que vas a realizar, tendrás histogramas, gráficos de barras, gráficos de pizza, gráficos de dispersión, gráficos de línea, entre otros.

La idea es que explores y experimentes con todos los recursos que te brindan Matplotlib y Seaborn.

Las siguientes preguntas se refieren al ranking Forbes 2000 considerando el periodo 2015 - 2022:

###A. ¿Cuál es el Top 10 de países con más empresas en Forbes para el periodo indicado?

```python
import pandas as pd

df_2015_2022 = df_concat

df_2015_2022
```

  <div id="df-1a8fa562-0d7d-4a4a-9d10-644d00463b16">
    <div class="colab-df-container">
      <div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }

</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>rank_nr</th>
      <th>Empresa</th>
      <th>Industria</th>
      <th>Pais</th>
      <th>Ingresos</th>
      <th>Ganancias</th>
      <th>Activos</th>
      <th>Valor de Mercado</th>
      <th>Margen de Rentabilidad</th>
      <th>Rentabilidad de los Activos (ROA)</th>
      <th>Año</th>
      <th>Codigo</th>
      <th>Continente</th>
      <th>Empleados</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>9</th>
      <td>13</td>
      <td>royal dutch shell</td>
      <td>oil &amp; gas operations</td>
      <td>Netherlands</td>
      <td>420371.0</td>
      <td>14884.1</td>
      <td>353116.0</td>
      <td>195380.0</td>
      <td>0.035407</td>
      <td>0.042151</td>
      <td>2015</td>
      <td>NLD</td>
      <td>Europe</td>
      <td>94000</td>
    </tr>
    <tr>
      <th>10</th>
      <td>15</td>
      <td>hsbc holdings</td>
      <td>banking</td>
      <td>United Kingdom</td>
      <td>81086.0</td>
      <td>13536.7</td>
      <td>2634139.0</td>
      <td>167746.0</td>
      <td>0.166943</td>
      <td>0.005139</td>
      <td>2015</td>
      <td>GBR</td>
      <td>Europe</td>
      <td>264767</td>
    </tr>
    <tr>
      <th>14</th>
      <td>21</td>
      <td>allianz</td>
      <td>insurance</td>
      <td>Germany</td>
      <td>128401.0</td>
      <td>8250.5</td>
      <td>978980.0</td>
      <td>82007.0</td>
      <td>0.064256</td>
      <td>0.008428</td>
      <td>2015</td>
      <td>DEU</td>
      <td>Europe</td>
      <td>147425</td>
    </tr>
    <tr>
      <th>16</th>
      <td>26</td>
      <td>daimler</td>
      <td>consumer durables</td>
      <td>Germany</td>
      <td>172268.0</td>
      <td>9234.7</td>
      <td>229468.0</td>
      <td>103272.0</td>
      <td>0.053607</td>
      <td>0.040244</td>
      <td>2015</td>
      <td>DEU</td>
      <td>Europe</td>
      <td>279972</td>
    </tr>
    <tr>
      <th>20</th>
      <td>31</td>
      <td>banco santander</td>
      <td>banking</td>
      <td>Spain</td>
      <td>56361.0</td>
      <td>7714.6</td>
      <td>1532282.0</td>
      <td>109351.0</td>
      <td>0.136878</td>
      <td>0.005035</td>
      <td>2015</td>
      <td>ESP</td>
      <td>Europe</td>
      <td>185405</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>2307</th>
      <td>1513</td>
      <td>performance food group</td>
      <td>food markets</td>
      <td>United States</td>
      <td>39732.0</td>
      <td>36.9</td>
      <td>12220.0</td>
      <td>8130.0</td>
      <td>0.000929</td>
      <td>0.003020</td>
      <td>2022</td>
      <td>USA</td>
      <td>North America</td>
      <td>22885</td>
    </tr>
    <tr>
      <th>2308</th>
      <td>1529</td>
      <td>us foods</td>
      <td>food markets</td>
      <td>United States</td>
      <td>29487.0</td>
      <td>164.0</td>
      <td>12521.0</td>
      <td>8523.0</td>
      <td>0.005562</td>
      <td>0.013098</td>
      <td>2022</td>
      <td>USA</td>
      <td>North America</td>
      <td>28000</td>
    </tr>
    <tr>
      <th>2309</th>
      <td>1548</td>
      <td>medipal holdings</td>
      <td>drugs &amp; biotechnology</td>
      <td>Japan</td>
      <td>29849.0</td>
      <td>331.4</td>
      <td>15444.0</td>
      <td>3349.0</td>
      <td>0.011103</td>
      <td>0.021458</td>
      <td>2022</td>
      <td>JPN</td>
      <td>Asia</td>
      <td>14454</td>
    </tr>
    <tr>
      <th>2310</th>
      <td>1640</td>
      <td>world fuel services</td>
      <td>trading companies</td>
      <td>United States</td>
      <td>31300.0</td>
      <td>73.6</td>
      <td>5942.0</td>
      <td>1715.0</td>
      <td>0.002351</td>
      <td>0.012386</td>
      <td>2022</td>
      <td>USA</td>
      <td>North America</td>
      <td>4414</td>
    </tr>
    <tr>
      <th>2311</th>
      <td>1656</td>
      <td>rajesh exports</td>
      <td>consumer durables</td>
      <td>India</td>
      <td>30005.0</td>
      <td>157.3</td>
      <td>2696.0</td>
      <td>2496.0</td>
      <td>0.005242</td>
      <td>0.058346</td>
      <td>2022</td>
      <td>IND</td>
      <td>Asia</td>
      <td>181</td>
    </tr>
  </tbody>
</table>
<p>2284 rows × 14 columns</p>
</div>
      <button class="colab-df-convert" onclick="convertToInteractive('df-1a8fa562-0d7d-4a4a-9d10-644d00463b16')"
              title="Convert this dataframe to an interactive table."
              style="display:none;">

<svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
width="24px">
<path d="M0 0h24v24H0V0z" fill="none"/>
<path d="M18.56 5.44l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94zm-11 1L8.5 8.5l.94-2.06 2.06-.94-2.06-.94L8.5 2.5l-.94 2.06-2.06.94zm10 10l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94z"/><path d="M17.41 7.96l-1.37-1.37c-.4-.4-.92-.59-1.43-.59-.52 0-1.04.2-1.43.59L10.3 9.45l-7.72 7.72c-.78.78-.78 2.05 0 2.83L4 21.41c.39.39.9.59 1.41.59.51 0 1.02-.2 1.41-.59l7.78-7.78 2.81-2.81c.8-.78.8-2.07 0-2.86zM5.41 20L4 18.59l7.72-7.72 1.47 1.35L5.41 20z"/>
</svg>
</button>

  <style>
    .colab-df-container {
      display:flex;
      flex-wrap:wrap;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

      <script>
        const buttonEl =
          document.querySelector('#df-1a8fa562-0d7d-4a4a-9d10-644d00463b16 button.colab-df-convert');
        buttonEl.style.display =
          google.colab.kernel.accessAllowed ? 'block' : 'none';

        async function convertToInteractive(key) {
          const element = document.querySelector('#df-1a8fa562-0d7d-4a4a-9d10-644d00463b16');
          const dataTable =
            await google.colab.kernel.invokeFunction('convertToInteractive',
                                                     [key], {});
          if (!dataTable) return;

          const docLinkHtml = 'Like what you see? Visit the ' +
            '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
            + ' to learn more about interactive tables.';
          element.innerHTML = '';
          dataTable['output_type'] = 'display_data';
          await google.colab.output.renderOutput(dataTable, element);
          const docLink = document.createElement('div');
          docLink.innerHTML = docLinkHtml;
          element.appendChild(docLink);
        }
      </script>
    </div>

  </div>

```python
import pandas as pd

# Obtener el Top 10 de países con más empresas
top_10_paises_b = pd.DataFrame(df_2015_2022['Pais'].value_counts().head(10)).reset_index()

# Renombrar las columnas
top_10_paises_b= top_10_paises_b.rename(columns={'index': 'Pais', 'Pais': '#de Empresas'})

top_10_paises_b
```

  <div id="df-cb0cc625-defc-48d8-b9c6-38af40c3b662">
    <div class="colab-df-container">
      <div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }

</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Pais</th>
      <th>#de Empresas</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>United States</td>
      <td>773</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Japan</td>
      <td>297</td>
    </tr>
    <tr>
      <th>2</th>
      <td>China</td>
      <td>185</td>
    </tr>
    <tr>
      <th>3</th>
      <td>France</td>
      <td>136</td>
    </tr>
    <tr>
      <th>4</th>
      <td>United Kingdom</td>
      <td>133</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Germany</td>
      <td>116</td>
    </tr>
    <tr>
      <th>6</th>
      <td>South Korea</td>
      <td>102</td>
    </tr>
    <tr>
      <th>7</th>
      <td>Canada</td>
      <td>72</td>
    </tr>
    <tr>
      <th>8</th>
      <td>India</td>
      <td>56</td>
    </tr>
    <tr>
      <th>9</th>
      <td>Switzerland</td>
      <td>51</td>
    </tr>
  </tbody>
</table>
</div>
      <button class="colab-df-convert" onclick="convertToInteractive('df-cb0cc625-defc-48d8-b9c6-38af40c3b662')"
              title="Convert this dataframe to an interactive table."
              style="display:none;">

<svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
width="24px">
<path d="M0 0h24v24H0V0z" fill="none"/>
<path d="M18.56 5.44l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94zm-11 1L8.5 8.5l.94-2.06 2.06-.94-2.06-.94L8.5 2.5l-.94 2.06-2.06.94zm10 10l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94z"/><path d="M17.41 7.96l-1.37-1.37c-.4-.4-.92-.59-1.43-.59-.52 0-1.04.2-1.43.59L10.3 9.45l-7.72 7.72c-.78.78-.78 2.05 0 2.83L4 21.41c.39.39.9.59 1.41.59.51 0 1.02-.2 1.41-.59l7.78-7.78 2.81-2.81c.8-.78.8-2.07 0-2.86zM5.41 20L4 18.59l7.72-7.72 1.47 1.35L5.41 20z"/>
</svg>
</button>

  <style>
    .colab-df-container {
      display:flex;
      flex-wrap:wrap;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

      <script>
        const buttonEl =
          document.querySelector('#df-cb0cc625-defc-48d8-b9c6-38af40c3b662 button.colab-df-convert');
        buttonEl.style.display =
          google.colab.kernel.accessAllowed ? 'block' : 'none';

        async function convertToInteractive(key) {
          const element = document.querySelector('#df-cb0cc625-defc-48d8-b9c6-38af40c3b662');
          const dataTable =
            await google.colab.kernel.invokeFunction('convertToInteractive',
                                                     [key], {});
          if (!dataTable) return;

          const docLinkHtml = 'Like what you see? Visit the ' +
            '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
            + ' to learn more about interactive tables.';
          element.innerHTML = '';
          dataTable['output_type'] = 'display_data';
          await google.colab.output.renderOutput(dataTable, element);
          const docLink = document.createElement('div');
          docLink.innerHTML = docLinkHtml;
          element.appendChild(docLink);
        }
      </script>
    </div>

  </div>

```python
import seaborn as sns
import matplotlib.pyplot as plt

# Definir el tamaño del gráfico
plt.figure(figsize=(15, 8))

# Crear el gráfico de barras
sns.barplot(data=top_10_paises_b, y='Pais', x='#de Empresas', palette='rocket', label='Empresas por país')

# Agregar título y subtítulo
plt.title('Top 10 países con más empresas', fontsize=20)
plt.suptitle('Datos de 2015 a 2022', fontsize=16)

# Agregar etiquetas a los ejes
plt.xlabel('Número de empresas', fontsize=14)
plt.ylabel('País', fontsize=14)

# Ajustar el tamaño de la fuente de la leyenda
plt.legend(fontsize=12)

# Mostrar el gráfico
plt.show()
```

![png](Data_Insider_files/Data_Insider_98_0.png)

###B. ¿Cuál es el Top 5 de países con más empresas en el área de tecnología y de telecomunicaciones?

```python
# Seleccionar las empresas del área de tecnología y de telecomunicaciones
tecnologia_telecomunicaciones = df_2015_2022[df_2015_2022['Industria'].str.contains('technology hardware & equipment|telecommunication services')]

# Obtener el Top 4 de países con más empresas en el área de tecnología y de telecomunicaciones
top_5_paises_tec_telecom = pd.DataFrame(tecnologia_telecomunicaciones['Pais'].value_counts().head(5))

# Renombrar las columnas
top_5_paises_tec_telecom = top_5_paises_tec_telecom.rename(columns={'Pais': '+ Empresas'})

# Cambiar el nombre del índice
top_5_paises_tec_telecom.index.name = 'Pais'

top_5_paises_tec_telecom
```

  <div id="df-0f0141d1-9275-4251-a4dc-50f77d89592c">
    <div class="colab-df-container">
      <div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }

</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>+ Empresas</th>
    </tr>
    <tr>
      <th>Pais</th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>United States</th>
      <td>48</td>
    </tr>
    <tr>
      <th>Taiwan</th>
      <td>25</td>
    </tr>
    <tr>
      <th>Japan</th>
      <td>20</td>
    </tr>
    <tr>
      <th>France</th>
      <td>9</td>
    </tr>
    <tr>
      <th>Germany</th>
      <td>8</td>
    </tr>
  </tbody>
</table>
</div>
      <button class="colab-df-convert" onclick="convertToInteractive('df-0f0141d1-9275-4251-a4dc-50f77d89592c')"
              title="Convert this dataframe to an interactive table."
              style="display:none;">

<svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
width="24px">
<path d="M0 0h24v24H0V0z" fill="none"/>
<path d="M18.56 5.44l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94zm-11 1L8.5 8.5l.94-2.06 2.06-.94-2.06-.94L8.5 2.5l-.94 2.06-2.06.94zm10 10l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94z"/><path d="M17.41 7.96l-1.37-1.37c-.4-.4-.92-.59-1.43-.59-.52 0-1.04.2-1.43.59L10.3 9.45l-7.72 7.72c-.78.78-.78 2.05 0 2.83L4 21.41c.39.39.9.59 1.41.59.51 0 1.02-.2 1.41-.59l7.78-7.78 2.81-2.81c.8-.78.8-2.07 0-2.86zM5.41 20L4 18.59l7.72-7.72 1.47 1.35L5.41 20z"/>
</svg>
</button>

  <style>
    .colab-df-container {
      display:flex;
      flex-wrap:wrap;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

      <script>
        const buttonEl =
          document.querySelector('#df-0f0141d1-9275-4251-a4dc-50f77d89592c button.colab-df-convert');
        buttonEl.style.display =
          google.colab.kernel.accessAllowed ? 'block' : 'none';

        async function convertToInteractive(key) {
          const element = document.querySelector('#df-0f0141d1-9275-4251-a4dc-50f77d89592c');
          const dataTable =
            await google.colab.kernel.invokeFunction('convertToInteractive',
                                                     [key], {});
          if (!dataTable) return;

          const docLinkHtml = 'Like what you see? Visit the ' +
            '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
            + ' to learn more about interactive tables.';
          element.innerHTML = '';
          dataTable['output_type'] = 'display_data';
          await google.colab.output.renderOutput(dataTable, element);
          const docLink = document.createElement('div');
          docLink.innerHTML = docLinkHtml;
          element.appendChild(docLink);
        }
      </script>
    </div>

  </div>

```python
import seaborn as sns
import matplotlib.pyplot as plt

# Definir el tamaño del gráfico
plt.figure(figsize=(15, 8))

# Crear el gráfico de dispersión
sns.scatterplot(data=top_5_paises_tec_telecom.reset_index(), x='Pais', y='+ Empresas', s=200, color='red', label='Empresas por país')

# Agregar título y subtítulo
plt.title('Top 5 países con más empresas en tecnología y telecomunicaciones', fontsize=20)
plt.suptitle('Datos de 2015 a 2022', fontsize=16)

# Agregar etiquetas a los ejes
plt.xlabel('País', fontsize=14)
plt.ylabel('Número de empresas', fontsize=14)

# Ajustar el tamaño de la fuente de la leyenda
plt.legend(fontsize=12)

# Mostrar el gráfico
plt.show()
```

![png](Data_Insider_files/Data_Insider_101_0.png)

###C. ¿Cuál fue el margen de pérdida de las 10 empresas que presentaron mayores perjuicios considerando el total de pérdidas registradas en la Industria de los Hoteles, Restaurantes y entretenimiento?

```python
import pandas as pd

# Filtrar el DataFrame original por Empresa, Industria, Ingresos y Ganancias
hoteles_restaurantes_entretenimiento = df_2015_2022[['Empresa', 'Industria', 'Ingresos', 'Ganancias','Activos']]

# Filtrar el DataFrame por Industria = hotels, restaurants & leisure
df_hotels_b = hoteles_restaurantes_entretenimiento[hoteles_restaurantes_entretenimiento['Industria'] == 'hotels, restaurants & leisure']

# Agrupar el DataFrame por Empresa y sumar los Ingresos y las Ganancias por empresa
df_hotels_grouped_b = df_hotels_b.groupby('Empresa').agg({'Ingresos': 'sum', 'Ganancias': 'sum', 'Activos': 'sum'})

# Agrupar por industria y empresa, y calcular las pérdidas
df_hotels_grouped_b['Costos'] = df_hotels_grouped_b['Activos'] - df_hotels_grouped_b['Ganancias']
df_hotels_grouped_b['Perdida = Costos - Ingresos'] = df_hotels_grouped_b['Costos'] - df_hotels_grouped_b['Ingresos']

# Calcular el margen de pérdida por empresa y ordenar de mayor a menor
df_hotels_grouped_b['Margen de Perdida = Costos / Ingresos'] = ((df_hotels_grouped_b['Costos']) / df_hotels_grouped_b['Ingresos']) * 100
df_hotels_grouped_b['Margen de Perdida = Costos / Ingresos'] = df_hotels_grouped_b['Margen de Perdida = Costos / Ingresos'].round(1)
df_mayores_perdidas = df_hotels_grouped_b.sort_values(by=['Perdida = Costos - Ingresos', 'Margen de Perdida = Costos / Ingresos'], ascending=[True, False])

# Filtrar el DataFrame por pérdidas negativas y mostrar solo las 10 primeras empresas
df_mayores_perdidas_negativas = df_mayores_perdidas.loc[df_mayores_perdidas['Perdida = Costos - Ingresos'] < 0].head(10)

# Mostrar el DataFrame con Empresa, Ingresos, Ganancias, Costos, Perdida y Margen de Pérdida
df_mayores_perdidas_negativas = df_mayores_perdidas_negativas[['Ingresos', 'Ganancias', 'Activos', 'Costos', 'Perdida = Costos - Ingresos', 'Margen de Perdida = Costos / Ingresos']]

df_mayores_perdidas_negativas
```

  <div id="df-f64cf610-efab-4c18-9be4-3b039932ba44">
    <div class="colab-df-container">
      <div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }

</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Ingresos</th>
      <th>Ganancias</th>
      <th>Activos</th>
      <th>Costos</th>
      <th>Perdida = Costos - Ingresos</th>
      <th>Margen de Perdida = Costos / Ingresos</th>
    </tr>
    <tr>
      <th>Empresa</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>compass group</th>
      <td>201028.0</td>
      <td>8793.1</td>
      <td>108931.0</td>
      <td>100137.9</td>
      <td>-100890.1</td>
      <td>49.8</td>
    </tr>
    <tr>
      <th>starbucks</th>
      <td>57014.0</td>
      <td>7782.9</td>
      <td>56313.0</td>
      <td>48530.1</td>
      <td>-8483.9</td>
      <td>85.1</td>
    </tr>
  </tbody>
</table>
</div>
      <button class="colab-df-convert" onclick="convertToInteractive('df-f64cf610-efab-4c18-9be4-3b039932ba44')"
              title="Convert this dataframe to an interactive table."
              style="display:none;">

<svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
width="24px">
<path d="M0 0h24v24H0V0z" fill="none"/>
<path d="M18.56 5.44l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94zm-11 1L8.5 8.5l.94-2.06 2.06-.94-2.06-.94L8.5 2.5l-.94 2.06-2.06.94zm10 10l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94z"/><path d="M17.41 7.96l-1.37-1.37c-.4-.4-.92-.59-1.43-.59-.52 0-1.04.2-1.43.59L10.3 9.45l-7.72 7.72c-.78.78-.78 2.05 0 2.83L4 21.41c.39.39.9.59 1.41.59.51 0 1.02-.2 1.41-.59l7.78-7.78 2.81-2.81c.8-.78.8-2.07 0-2.86zM5.41 20L4 18.59l7.72-7.72 1.47 1.35L5.41 20z"/>
</svg>
</button>

  <style>
    .colab-df-container {
      display:flex;
      flex-wrap:wrap;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

      <script>
        const buttonEl =
          document.querySelector('#df-f64cf610-efab-4c18-9be4-3b039932ba44 button.colab-df-convert');
        buttonEl.style.display =
          google.colab.kernel.accessAllowed ? 'block' : 'none';

        async function convertToInteractive(key) {
          const element = document.querySelector('#df-f64cf610-efab-4c18-9be4-3b039932ba44');
          const dataTable =
            await google.colab.kernel.invokeFunction('convertToInteractive',
                                                     [key], {});
          if (!dataTable) return;

          const docLinkHtml = 'Like what you see? Visit the ' +
            '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
            + ' to learn more about interactive tables.';
          element.innerHTML = '';
          dataTable['output_type'] = 'display_data';
          await google.colab.output.renderOutput(dataTable, element);
          const docLink = document.createElement('div');
          docLink.innerHTML = docLinkHtml;
          element.appendChild(docLink);
        }
      </script>
    </div>

  </div>

```python
# Crear el gráfico de barras verticales
plt.figure(figsize=(8, 10))

sns.set_style('whitegrid')

sns.barplot(x='Empresa', y='Ingresos', data=df_mayores_perdidas_negativas.reset_index(), color='gold', label='Ingresos')
sns.barplot(x='Empresa', y='Costos', data=df_mayores_perdidas_negativas.reset_index(), color='coral', label='Costos')
sns.barplot(x='Empresa', y='Perdida = Costos - Ingresos', data=df_mayores_perdidas_negativas.reset_index(), color='brown', label='Pérdidas')
sns.barplot(x='Empresa', y='Ganancias', data=df_mayores_perdidas_negativas.reset_index(), color='limegreen', label='Ganancias')
sns.barplot(x='Empresa', y='Margen de Perdida = Costos / Ingresos', data=df_mayores_perdidas_negativas.reset_index(), color='indigo', label='Margen de Pérdida')

plt.xticks(rotation=90)
plt.title('Top 10 empresas con mayores pérdidas en la industria de hoteles, restaurantes y entretenimiento')
plt.xlabel('Empresa')
plt.ylabel('Monto')

# Agregar valores de margen de pérdida encima de cada barra
for i in range(len(df_mayores_perdidas_negativas)):
    margen = df_mayores_perdidas_negativas['Margen de Perdida = Costos / Ingresos'][i]
    plt.text(i, df_mayores_perdidas_negativas['Ganancias'][i] + 1,
             str(margen) + '%', fontsize=12, color='white', backgroundcolor='indigo')
    plt.axvspan(i - 0.4, i + 0.4, facecolor='indigo', alpha=0.2)

# Mover leyenda a la parte superior derecha del gráfico
plt.legend(loc='upper right', fontsize=12)

plt.show()
```

![png](Data_Insider_files/Data_Insider_104_0.png)

###D. Considerando a la Industria Petrolera en las Américas, ¿Cuál o cuáles empresas superaron en más del 20% la rentabilidad de sus activos?

```python
import pandas as pd

petrolera_americas = df_2015_2022[(df_2015_2022['Industria'] == 'oil & gas operations') & (df_2015_2022['Continente'].isin(['North America', 'South America']))].copy()

# Agrupar el DataFrame por Empresa y sumar los Ingresos y las Ganancias por empresa
petrolera_americas_por_empresa = petrolera_americas.groupby('Empresa').agg({'Margen de Rentabilidad': 'sum', 'Activos': 'sum'})
petrolera_americas_b = petrolera_americas_por_empresa.sort_values(by=['Margen de Rentabilidad', 'Activos'], ascending=[False, False])

empresas_superiores_20 = petrolera_americas_b[petrolera_americas_b['Margen de Rentabilidad'] >= 0.2]

# Agregar columnas de País y Continente
empresas_superiores_20 = pd.merge(empresas_superiores_20, df_2015_2022[['Empresa', 'Pais', 'Continente']], on='Empresa').drop_duplicates()

# Seleccionar columnas de interés
empresas_superiores_20 = empresas_superiores_20[['Empresa', 'Pais', 'Continente', 'Activos', 'Margen de Rentabilidad']]

empresas_superiores_20
```

  <div id="df-484454cf-7c2f-4f5c-9ca8-e83af94bf59d">
    <div class="colab-df-container">
      <div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }

</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Empresa</th>
      <th>Pais</th>
      <th>Continente</th>
      <th>Activos</th>
      <th>Margen de Rentabilidad</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>enbridge</td>
      <td>Canada</td>
      <td>North America</td>
      <td>824824.0</td>
      <td>0.566855</td>
    </tr>
    <tr>
      <th>8</th>
      <td>suncor energy</td>
      <td>Canada</td>
      <td>North America</td>
      <td>396246.0</td>
      <td>0.383611</td>
    </tr>
    <tr>
      <th>14</th>
      <td>chevron</td>
      <td>United States</td>
      <td>North America</td>
      <td>2019265.0</td>
      <td>0.359491</td>
    </tr>
    <tr>
      <th>22</th>
      <td>conocophillips</td>
      <td>United States</td>
      <td>North America</td>
      <td>600196.0</td>
      <td>0.282121</td>
    </tr>
    <tr>
      <th>29</th>
      <td>petrobras</td>
      <td>Brazil</td>
      <td>South America</td>
      <td>1838485.0</td>
      <td>0.258494</td>
    </tr>
  </tbody>
</table>
</div>
      <button class="colab-df-convert" onclick="convertToInteractive('df-484454cf-7c2f-4f5c-9ca8-e83af94bf59d')"
              title="Convert this dataframe to an interactive table."
              style="display:none;">

<svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
width="24px">
<path d="M0 0h24v24H0V0z" fill="none"/>
<path d="M18.56 5.44l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94zm-11 1L8.5 8.5l.94-2.06 2.06-.94-2.06-.94L8.5 2.5l-.94 2.06-2.06.94zm10 10l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94z"/><path d="M17.41 7.96l-1.37-1.37c-.4-.4-.92-.59-1.43-.59-.52 0-1.04.2-1.43.59L10.3 9.45l-7.72 7.72c-.78.78-.78 2.05 0 2.83L4 21.41c.39.39.9.59 1.41.59.51 0 1.02-.2 1.41-.59l7.78-7.78 2.81-2.81c.8-.78.8-2.07 0-2.86zM5.41 20L4 18.59l7.72-7.72 1.47 1.35L5.41 20z"/>
</svg>
</button>

  <style>
    .colab-df-container {
      display:flex;
      flex-wrap:wrap;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

      <script>
        const buttonEl =
          document.querySelector('#df-484454cf-7c2f-4f5c-9ca8-e83af94bf59d button.colab-df-convert');
        buttonEl.style.display =
          google.colab.kernel.accessAllowed ? 'block' : 'none';

        async function convertToInteractive(key) {
          const element = document.querySelector('#df-484454cf-7c2f-4f5c-9ca8-e83af94bf59d');
          const dataTable =
            await google.colab.kernel.invokeFunction('convertToInteractive',
                                                     [key], {});
          if (!dataTable) return;

          const docLinkHtml = 'Like what you see? Visit the ' +
            '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
            + ' to learn more about interactive tables.';
          element.innerHTML = '';
          dataTable['output_type'] = 'display_data';
          await google.colab.output.renderOutput(dataTable, element);
          const docLink = document.createElement('div');
          docLink.innerHTML = docLinkHtml;
          element.appendChild(docLink);
        }
      </script>
    </div>

  </div>

```python
import numpy as np
import matplotlib.pyplot as plt
import matplotlib.ticker as mtick
import seaborn as sns

# Crear el gráfico personalizado
plt.figure(figsize=(15, 8))

sns.set_style('darkgrid')

# Crear scatterplot con empresas con margen de rentabilidad en el eje x, activos en el eje y y margen de rentabilidad como el tamaño de los puntos
sns.scatterplot(data=empresas_superiores_20, x='Margen de Rentabilidad', y='Activos', hue='Empresa', size='Margen de Rentabilidad', sizes=(300, 3000), alpha=0.7, palette='bright')

# Convertir margen de rentabilidad a porcentaje
plt.gca().xaxis.set_major_formatter(mtick.PercentFormatter(xmax=1, decimals=0))

# Establecer título, subtítulo, nombres de los ejes y leyenda
plt.title('Empresas petroleras en América con margen de rentabilidad superior al 20%')
plt.suptitle('Relación entre margen de rentabilidad, empresa y activos', fontsize=14, y=0.95)
plt.xlabel('Margen de rentabilidad')
plt.ylabel('Activos (en millones)')

# Crear nueva lista de etiquetas para la leyenda
etiquetas = [f"{row['Empresa']} ({row['Pais']})" for _, row in empresas_superiores_20.iterrows()]

# Establecer leyenda con las nuevas etiquetas
plt.legend(title='Empresa (País)', fontsize=10, labels=etiquetas, markerscale=0, scatterpoints=1)

# Establecer tamaño de fuente para los ejes
plt.xticks(fontsize=10, rotation=0)
plt.yticks(fontsize=10)

# Especificar ubicación de las etiquetas en los ejes
# plt.xticks(np.arange(0, 0.4, 0.05))
# plt.yticks(np.arange(0, 60000000000, 10000000000))

# Cambiar unidades de los activos a millones y mostrar dos decimales
ax = plt.gca()
ax.set_xticklabels([f"{int(x*100)}%" for x in ax.get_xticks()])
ax.set_yticklabels([f"{round(x/1e6, 1)}M" for x in ax.get_yticks()])

# Agregar el nombre de cada empresa en su respectiva burbuja
for _, row in empresas_superiores_20.iterrows():
    plt.annotate(row['Empresa'], xy=(row['Margen de Rentabilidad'], row['Activos']), size=9, ha='center', va='center')

# Mostrar gráfico
plt.show()
```

    <ipython-input-68-207e3c864575>:39: UserWarning: FixedFormatter should only be used together with FixedLocator
      ax.set_xticklabels([f"{int(x*100)}%" for x in ax.get_xticks()])
    <ipython-input-68-207e3c864575>:40: UserWarning: FixedFormatter should only be used together with FixedLocator
      ax.set_yticklabels([f"{round(x/1e6, 1)}M" for x in ax.get_yticks()])

![png](Data_Insider_files/Data_Insider_107_1.png)

###E. ¿Cuáles fueron las empresas europeas con el mayor porcentaje de rentabilidad por industria?

```python
import pandas as pd

# Filtrar el DataFrame por continente Europe y agrupar por empresa e industria
df_europe = df_2015_2022[df_2015_2022['Continente'] == 'Europe'].groupby(['Empresa', 'Industria']).agg({'Ingresos': 'sum', 'Activos': 'sum', 'Margen de Rentabilidad': 'mean'})

# Seleccionar la empresa con mayor margen de rentabilidad para cada industria
empresas_max_rentabilidad_europe = df_europe.loc[df_europe.groupby('Industria')['Margen de Rentabilidad'].idxmax()].reset_index()

# Ordenar las empresas por margen de rentabilidad de forma descendente
empresas_max_rentabilidad_europe = empresas_max_rentabilidad_europe.sort_values('Margen de Rentabilidad', ascending=False)

# Seleccionar las columnas que se desean mostrar
empresas_max_rentabilidad_europe = empresas_max_rentabilidad_europe[['Industria', 'Empresa', 'Ingresos', 'Activos', 'Margen de Rentabilidad']]

# Mostrar el DataFrame resultante
print(empresas_max_rentabilidad_europe.to_string(index=False))
```

                           Industria                        Empresa  Ingresos    Activos  Margen de Rentabilidad
               food, drink & tobacco       british american tobacco  127125.0   750020.0                0.645179
          telecommunication services                        vivendi   14497.0    43395.0                0.434731
               drugs & biotechnology                       novartis  402547.0  1060400.0                0.246620
              diversified financials                      ing group  101445.0  4243601.0                0.201417
              it software & services                            sap  200080.0   427006.0                0.169136
                   consumer durables            mercedes-benz group  178935.0   295480.0                0.151970
                             banking                  hsbc holdings  528076.0 21488941.0                0.139453
                           utilities                  national grid   70112.0   249642.0                0.139393
    health care equipment & services                      medtronic  180415.0   564004.0                0.136644
                           insurance                          chubb  208189.0  1023425.0                0.130542
                           materials                 anglo american  129800.0   236867.0                0.130277
                           retailing                        inditex   94824.0    88791.0                0.125795
                           chemicals                          bayer  152211.0   267795.0                0.122570
                       conglomerates                            abb  261715.0   343955.0                0.088264
                        construction                         holcim   29350.0    65725.0                0.084968
                       capital goods             schneider electric  241431.0   409446.0                0.082921
                 aerospace & defense                         safran   52895.0    94487.0                0.079268
                oil & gas operations                          shell  261761.0   404379.0                0.077419
       hotels, restaurants & leisure                  compass group  201028.0   108931.0                0.043114
        business services & supplies johnson controls international   82222.0   146756.0                0.041758
                         air courier                  deutsche post  140798.0    86602.0                0.031285
                        food markets                    royal ahold   85837.0    34358.0                0.023146
         diversified metals & mining                 anglo american   53249.0   120571.0                0.012499
     technology hardware & equipment                       ericsson   82230.0   101690.0               -0.000269
                   trading companies                        finatis  115225.0   117489.0               -0.011720

```python
import seaborn as sns
import matplotlib.pyplot as plt
import matplotlib.ticker as mtick

# Seleccionar las 5 empresas con mayor margen de rentabilidad
top_empresas = empresas_max_rentabilidad_europe.sort_values('Margen de Rentabilidad', ascending=False).head(5)

# Crear la gráfica
fig, ax = plt.subplots(figsize=(15, 8))
sns.scatterplot(x='Margen de Rentabilidad', y='Ingresos', hue='Margen de Rentabilidad', size='Margen de Rentabilidad', sizes=(50, 500), data=empresas_max_rentabilidad_europe, palette='viridis')

# Agregar título y subtítulo
plt.title('Relación entre Margen de Rentabilidad, Ingresos y Activos', fontsize=20)
plt.suptitle('Empresas en Europa', fontsize=16, y=0.95)

# Agregar etiquetas de los ejes
plt.xlabel('Margen de Rentabilidad (%)', fontsize=14)
plt.ylabel('Ingresos (en dolares)', fontsize=14)

# Cambiar tamaño de fuente de los ejes
plt.xticks(fontsize=12)
plt.yticks(fontsize=12)

# Cambiar los ticks del eje Y a millones
formatter = mtick.StrMethodFormatter('U${x:,.0f}')
ax.yaxis.set_major_formatter(formatter)

# Agregar el nombre de la empresa y los valores en porcentaje por encima de los 5 primeros puntos
for i, row in top_empresas.iterrows():
    margen_rentabilidad = f"{row['Margen de Rentabilidad']*100:.2f}%"
    ingresos = f"U${row['Ingresos']/1000000:.2f}M"
    plt.text(row['Margen de Rentabilidad'], row['Ingresos'] + 0.7 * (row['Margen de Rentabilidad'] / 100), f"{row['Empresa']} ({margen_rentabilidad})", fontsize=12, ha='center', va='bottom')

# Agregar leyenda de margen de rentabilidad
plt.legend(title='Margen de Rentabilidad (%)', fontsize=12, title_fontsize=14, loc='upper right')

# Agregar leyenda de activos
activos = [f"{row['Empresa']}: {row['Activos']/1000000:.2f} M" for i, row in top_empresas.iterrows()]
plt.figtext(.02, .92, 'Activos de las 5 primeras empresas: \n\n' + '\n'.join(activos), fontsize=12)

# Mostrar la gráfica
plt.show()
```

![png](Data_Insider_files/Data_Insider_110_0.png)

```python
import pandas as pd

# Filtrar por la empresa ExxonMobil y sumar sus ganancias
ganancias_exxonmobil = df_2015_2022[df_2015_2022['Empresa'] == 'novartis']['Margen de Rentabilidad']

ganancias_exxonmobil
```

    34      0.189308
    329     0.356992
    636     0.138079
    944     0.160363
    1241    0.243401
    1531    0.251238
    1807    0.166032
    2085    0.467546
    Name: Margen de Rentabilidad, dtype: float64

###F. ¿Cuáles fueron las 10 empresas norteamericanas con mayores pérdidas registradas por industria a nivel global?

```python
import pandas as pd

# Filtrar por ['Empresa', 'Industria', 'Ingresos', 'Activos', 'Ganancias', Continente]
df_filt_b = df_2015_2022[['Empresa', 'Industria', 'Ingresos', 'Activos', 'Ganancias', 'Continente']]

# Filtrar por ['Continente'] == 'North America'
empresas_industria_ganancias = df_filt_b[(df_filt_b['Continente'] == 'North America')]

# Agrupar por industria y empresa, y calcular las pérdidas
empresas_por_industria = empresas_industria_ganancias.groupby(['Industria', 'Empresa'], as_index=False).agg({'Ingresos': 'sum', 'Activos': 'sum', 'Ganancias': 'sum'})
empresas_por_industria['Costos'] = empresas_por_industria['Activos'] - empresas_por_industria['Ganancias']
empresas_por_industria['Perdidas'] = empresas_por_industria['Costos'] - empresas_por_industria['Ingresos']

# Encontrar la empresa con la mayor pérdida por industria
peores_empresas_por_industria = empresas_por_industria[empresas_por_industria['Perdidas'] < 0].groupby('Industria', as_index=False).apply(lambda x: x.loc[x['Perdidas'].idxmax()])

# Cambiar el nombre de las columnas 'Costos' y 'Perdidas'
peores_empresas_por_industria = peores_empresas_por_industria.rename(columns={'Costos': 'Costos = Activos - Ganancias', 'Perdidas': 'Perdidas = Costos - Ingresos'})

# Mostrar el DataFrame con la empresa con la mayor pérdida por industria
peores_empresas_por_industria = peores_empresas_por_industria[['Industria', 'Empresa', 'Ingresos', 'Activos', 'Ganancias', 'Costos = Activos - Ganancias', 'Perdidas = Costos - Ingresos']]
peores_empresas_por_industria = peores_empresas_por_industria.sort_values('Perdidas = Costos - Ingresos', ascending=True)

peores_empresas_por_industria
```

  <div id="df-3033312f-e3ff-476b-835f-4be90e6316cf">
    <div class="colab-df-container">
      <div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }

</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Industria</th>
      <th>Empresa</th>
      <th>Ingresos</th>
      <th>Activos</th>
      <th>Ganancias</th>
      <th>Costos = Activos - Ganancias</th>
      <th>Perdidas = Costos - Ingresos</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>16</th>
      <td>technology hardware &amp; equipment</td>
      <td>hp</td>
      <td>430475.0</td>
      <td>226749.0</td>
      <td>27122.0</td>
      <td>199627.0</td>
      <td>-230848.0</td>
    </tr>
    <tr>
      <th>8</th>
      <td>food, drink &amp; tobacco</td>
      <td>tyson foods</td>
      <td>331578.0</td>
      <td>235824.0</td>
      <td>16622.0</td>
      <td>219202.0</td>
      <td>-112376.0</td>
    </tr>
    <tr>
      <th>0</th>
      <td>aerospace &amp; defense</td>
      <td>lockheed martin</td>
      <td>439314.0</td>
      <td>376985.0</td>
      <td>37701.0</td>
      <td>339284.0</td>
      <td>-100030.0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>air courier</td>
      <td>fedex</td>
      <td>218112.0</td>
      <td>172559.0</td>
      <td>10029.0</td>
      <td>162530.0</td>
      <td>-55582.0</td>
    </tr>
    <tr>
      <th>11</th>
      <td>insurance</td>
      <td>cigna</td>
      <td>334824.0</td>
      <td>302567.0</td>
      <td>13823.0</td>
      <td>288744.0</td>
      <td>-46080.0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>banking</td>
      <td>intl fcstone</td>
      <td>56783.0</td>
      <td>12421.0</td>
      <td>58.7</td>
      <td>12362.3</td>
      <td>-44420.7</td>
    </tr>
    <tr>
      <th>12</th>
      <td>materials</td>
      <td>nucor</td>
      <td>65027.0</td>
      <td>46554.0</td>
      <td>10305.5</td>
      <td>36248.5</td>
      <td>-28778.5</td>
    </tr>
    <tr>
      <th>18</th>
      <td>transportation</td>
      <td>united parcel service</td>
      <td>71911.0</td>
      <td>50016.0</td>
      <td>4791.0</td>
      <td>45225.0</td>
      <td>-26686.0</td>
    </tr>
    <tr>
      <th>6</th>
      <td>drugs &amp; biotechnology</td>
      <td>anthem</td>
      <td>92095.0</td>
      <td>71571.0</td>
      <td>3750.0</td>
      <td>67821.0</td>
      <td>-24274.0</td>
    </tr>
    <tr>
      <th>7</th>
      <td>food markets</td>
      <td>united natural foods</td>
      <td>26983.0</td>
      <td>7490.0</td>
      <td>198.4</td>
      <td>7291.6</td>
      <td>-19691.4</td>
    </tr>
    <tr>
      <th>4</th>
      <td>consumer durables</td>
      <td>johnson controls</td>
      <td>79237.0</td>
      <td>62929.0</td>
      <td>1700.0</td>
      <td>61229.0</td>
      <td>-18008.0</td>
    </tr>
    <tr>
      <th>5</th>
      <td>diversified financials</td>
      <td>intl fcstone</td>
      <td>26256.0</td>
      <td>8711.0</td>
      <td>79.0</td>
      <td>8632.0</td>
      <td>-17624.0</td>
    </tr>
    <tr>
      <th>9</th>
      <td>health care equipment &amp; services</td>
      <td>aetna</td>
      <td>242152.0</td>
      <td>235169.0</td>
      <td>10185.3</td>
      <td>224983.7</td>
      <td>-17168.3</td>
    </tr>
    <tr>
      <th>17</th>
      <td>trading companies</td>
      <td>td synnex</td>
      <td>42145.0</td>
      <td>28723.0</td>
      <td>436.4</td>
      <td>28286.6</td>
      <td>-13858.4</td>
    </tr>
    <tr>
      <th>14</th>
      <td>oil &amp; gas operations</td>
      <td>andeavor</td>
      <td>38636.0</td>
      <td>28841.0</td>
      <td>1650.0</td>
      <td>27191.0</td>
      <td>-11445.0</td>
    </tr>
    <tr>
      <th>13</th>
      <td>media</td>
      <td>directv</td>
      <td>33260.0</td>
      <td>25459.0</td>
      <td>2756.0</td>
      <td>22703.0</td>
      <td>-10557.0</td>
    </tr>
    <tr>
      <th>10</th>
      <td>hotels, restaurants &amp; leisure</td>
      <td>starbucks</td>
      <td>57014.0</td>
      <td>56313.0</td>
      <td>7782.9</td>
      <td>48530.1</td>
      <td>-8483.9</td>
    </tr>
    <tr>
      <th>15</th>
      <td>retailing</td>
      <td>dollar tree</td>
      <td>25509.0</td>
      <td>20696.0</td>
      <td>1341.9</td>
      <td>19354.1</td>
      <td>-6154.9</td>
    </tr>
    <tr>
      <th>3</th>
      <td>capital goods</td>
      <td>emerson electric</td>
      <td>45940.0</td>
      <td>45276.0</td>
      <td>4744.0</td>
      <td>40532.0</td>
      <td>-5408.0</td>
    </tr>
  </tbody>
</table>
</div>
      <button class="colab-df-convert" onclick="convertToInteractive('df-3033312f-e3ff-476b-835f-4be90e6316cf')"
              title="Convert this dataframe to an interactive table."
              style="display:none;">

<svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
width="24px">
<path d="M0 0h24v24H0V0z" fill="none"/>
<path d="M18.56 5.44l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94zm-11 1L8.5 8.5l.94-2.06 2.06-.94-2.06-.94L8.5 2.5l-.94 2.06-2.06.94zm10 10l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94z"/><path d="M17.41 7.96l-1.37-1.37c-.4-.4-.92-.59-1.43-.59-.52 0-1.04.2-1.43.59L10.3 9.45l-7.72 7.72c-.78.78-.78 2.05 0 2.83L4 21.41c.39.39.9.59 1.41.59.51 0 1.02-.2 1.41-.59l7.78-7.78 2.81-2.81c.8-.78.8-2.07 0-2.86zM5.41 20L4 18.59l7.72-7.72 1.47 1.35L5.41 20z"/>
</svg>
</button>

  <style>
    .colab-df-container {
      display:flex;
      flex-wrap:wrap;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

      <script>
        const buttonEl =
          document.querySelector('#df-3033312f-e3ff-476b-835f-4be90e6316cf button.colab-df-convert');
        buttonEl.style.display =
          google.colab.kernel.accessAllowed ? 'block' : 'none';

        async function convertToInteractive(key) {
          const element = document.querySelector('#df-3033312f-e3ff-476b-835f-4be90e6316cf');
          const dataTable =
            await google.colab.kernel.invokeFunction('convertToInteractive',
                                                     [key], {});
          if (!dataTable) return;

          const docLinkHtml = 'Like what you see? Visit the ' +
            '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
            + ' to learn more about interactive tables.';
          element.innerHTML = '';
          dataTable['output_type'] = 'display_data';
          await google.colab.output.renderOutput(dataTable, element);
          const docLink = document.createElement('div');
          docLink.innerHTML = docLinkHtml;
          element.appendChild(docLink);
        }
      </script>
    </div>

  </div>

```python
import seaborn as sns
import matplotlib.pyplot as plt
import matplotlib.ticker as mtick

# Filtrar por ['Empresa', 'Industria', 'Ingresos', 'Activos', 'Ganancias', Continente]
df_filt_b = df_2015_2022[['Empresa', 'Industria', 'Ingresos', 'Activos', 'Ganancias', 'Continente']]

# Filtrar por ['Continente'] == 'North America'
empresas_industria_ganancias = df_filt_b[(df_filt_b['Continente'] == 'North America')]

# Agrupar por industria y empresa, y calcular las pérdidas y costos
empresas_por_industria = empresas_industria_ganancias.groupby(['Industria', 'Empresa'], as_index=False).agg({'Ingresos': 'sum', 'Activos': 'sum', 'Ganancias': 'sum'})
empresas_por_industria['Costos'] = empresas_por_industria['Activos'] - empresas_por_industria['Ganancias']
empresas_por_industria['Perdidas'] = empresas_por_industria['Costos'] - empresas_por_industria['Ingresos']

# Encontrar la empresa con la mayor pérdida por industria
peores_empresas_por_industria = empresas_por_industria[empresas_por_industria['Perdidas'] < 0].groupby('Industria', as_index=False).apply(lambda x: x.loc[x['Perdidas'].idxmax()])

# Cambiar el nombre de las columnas 'Costos' y 'Perdidas'
peores_empresas_por_industria = peores_empresas_por_industria.rename(columns={'Costos': 'Costos = Activos - Ganancias', 'Perdidas': 'Perdidas = Costos - Ingresos'})

# Ordenar las empresas por pérdidas de forma ascendente
peores_empresas_por_industria = peores_empresas_por_industria[['Industria', 'Empresa', 'Ingresos', 'Costos = Activos - Ganancias', 'Perdidas = Costos - Ingresos']]
peores_empresas_por_industria = peores_empresas_por_industria.sort_values('Perdidas = Costos - Ingresos', ascending=True)

# Crear la gráfica
plt.figure(figsize=(15, 8))
sns.set_style("whitegrid")
sns.set_palette("rocket")
ax = sns.barplot(x='Empresa', y='Perdidas = Costos - Ingresos', hue='Industria', data=peores_empresas_por_industria, edgecolor='black')
sns.barplot(x='Empresa', y='Costos = Activos - Ganancias', hue='Industria', data=peores_empresas_por_industria, alpha=0.5, color='lightgray', edgecolor='black')
plt.xticks(rotation=45, ha='right')

# Agregar título y subtítulo
plt.title('Empresas con mayores pérdidas y costos en Norteamérica', fontsize=20)
plt.suptitle('Agrupadas por Industria', fontsize=16, y=0.95)

# Agregar etiquetas de los ejes
plt.xlabel('Empresas', fontsize=14)
plt.ylabel('Miles de dólares', fontsize=14)

# Cambiar tamaño de fuente de los ejes
plt.xticks(fontsize=12)
plt.yticks(fontsize=12)

# Agregar leyenda personalizada
plt.text(0.02, 0.95, 'Costos', transform=ax.transAxes, fontsize=12, color='red')
plt.text(0.02, 0.04, 'Perdidas', transform=ax.transAxes, fontsize=12, color='red')

# Quitar leyenda por defecto
ax.get_legend().remove()

# Agregar separación de miles en el eje y
fmt = 'U${x:,.0f}'
tick = mtick.StrMethodFormatter(fmt)
ax.yaxis.set_major_formatter(tick)

# Mostrar la gráfica
plt.show()
```

![png](Data_Insider_files/Data_Insider_114_0.png)

```python
import pandas as pd

# Filtrar por la empresa ExxonMobil y sumar sus ganancias
ganancias_exxonmobil = df_2015_2022[df_2015_2022['Empresa'] == 'schlumberger']['Ganancias'].sum()

ganancias_exxonmobil
```

    -11707.0

###G. ¿Cuál fue la distribución de Ingresos y Activos con respecto a las ganancias de los bancos cuyos activos no superan los 15000 millones de dólares?

```python
import pandas as pd

# Filtrar solo las columnas necesarias
df_bancos = df_2015_2022[['Empresa', 'Industria', 'Ingresos', 'Activos', 'Ganancias', 'Margen de Rentabilidad', 'Rentabilidad de los Activos (ROA)']]

# Filtrar solo la industria Banking
df_bancos = df_bancos[df_bancos['Industria'] == 'banking']

# Agrupar por empresa y calcular el promedio de los 'Margen de Rentabilidad' y 'Rentabilidad de los Activos (ROA)'
df_bancos = df_bancos.groupby('Empresa').agg({
    'Ingresos': 'sum',
    'Activos': 'sum',
    'Ganancias': 'sum',
    'Margen de Rentabilidad': 'mean',
    'Rentabilidad de los Activos (ROA)': 'mean'
}).reset_index()

# Filtrar por empresas cuyos activos no superan los 30000 millones de dólares
df_bancos = df_bancos[df_bancos['Activos'] <= 15000]

# Ordenar el DataFrame por margen de rentabilidad y rentabilidad de los activos (ROA)
df_bancos = df_bancos.sort_values(by=['Rentabilidad de los Activos (ROA)','Margen de Rentabilidad'], ascending=[False, False])

# Seleccionar las columnas de interés
df_bancos = df_bancos[['Empresa', 'Ingresos', 'Activos', 'Ganancias', 'Margen de Rentabilidad', 'Rentabilidad de los Activos (ROA)']]

# Mostrar el DataFrame resultante
df_bancos
```

  <div id="df-27e15d3e-91a7-4f68-bb14-5d614000616e">
    <div class="colab-df-container">
      <div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }

</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Empresa</th>
      <th>Ingresos</th>
      <th>Activos</th>
      <th>Ganancias</th>
      <th>Margen de Rentabilidad</th>
      <th>Rentabilidad de los Activos (ROA)</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>23</th>
      <td>intl fcstone</td>
      <td>56783.0</td>
      <td>12421.0</td>
      <td>58.7</td>
      <td>0.001176</td>
      <td>0.005499</td>
    </tr>
  </tbody>
</table>
</div>
      <button class="colab-df-convert" onclick="convertToInteractive('df-27e15d3e-91a7-4f68-bb14-5d614000616e')"
              title="Convert this dataframe to an interactive table."
              style="display:none;">

<svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
width="24px">
<path d="M0 0h24v24H0V0z" fill="none"/>
<path d="M18.56 5.44l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94zm-11 1L8.5 8.5l.94-2.06 2.06-.94-2.06-.94L8.5 2.5l-.94 2.06-2.06.94zm10 10l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94z"/><path d="M17.41 7.96l-1.37-1.37c-.4-.4-.92-.59-1.43-.59-.52 0-1.04.2-1.43.59L10.3 9.45l-7.72 7.72c-.78.78-.78 2.05 0 2.83L4 21.41c.39.39.9.59 1.41.59.51 0 1.02-.2 1.41-.59l7.78-7.78 2.81-2.81c.8-.78.8-2.07 0-2.86zM5.41 20L4 18.59l7.72-7.72 1.47 1.35L5.41 20z"/>
</svg>
</button>

  <style>
    .colab-df-container {
      display:flex;
      flex-wrap:wrap;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

      <script>
        const buttonEl =
          document.querySelector('#df-27e15d3e-91a7-4f68-bb14-5d614000616e button.colab-df-convert');
        buttonEl.style.display =
          google.colab.kernel.accessAllowed ? 'block' : 'none';

        async function convertToInteractive(key) {
          const element = document.querySelector('#df-27e15d3e-91a7-4f68-bb14-5d614000616e');
          const dataTable =
            await google.colab.kernel.invokeFunction('convertToInteractive',
                                                     [key], {});
          if (!dataTable) return;

          const docLinkHtml = 'Like what you see? Visit the ' +
            '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
            + ' to learn more about interactive tables.';
          element.innerHTML = '';
          dataTable['output_type'] = 'display_data';
          await google.colab.output.renderOutput(dataTable, element);
          const docLink = document.createElement('div');
          docLink.innerHTML = docLinkHtml;
          element.appendChild(docLink);
        }
      </script>
    </div>

  </div>

```python
import seaborn as sns
import matplotlib.pyplot as plt
import matplotlib.ticker as mtick

# Filtrar solo las columnas necesarias
df_bancos = df_2015_2022[['Empresa', 'Industria', 'Ingresos', 'Activos', 'Ganancias', 'Margen de Rentabilidad', 'Rentabilidad de los Activos (ROA)']]

# Filtrar solo la industria Banking
df_bancos = df_bancos[df_bancos['Industria'] == 'banking']

# Agrupar por empresa y calcular el promedio de los 'Margen de Rentabilidad' y 'Rentabilidad de los Activos (ROA)'
df_bancos = df_bancos.groupby('Empresa').agg({
    'Ingresos': 'sum',
    'Activos': 'sum',
    'Ganancias': 'sum',
    'Margen de Rentabilidad': 'mean',
    'Rentabilidad de los Activos (ROA)': 'mean'
}).reset_index()

# Ordenar el DataFrame por margen de rentabilidad y rentabilidad de los activos (ROA)
df_bancos = df_bancos.sort_values(by=['Rentabilidad de los Activos (ROA)','Margen de Rentabilidad'], ascending=[False, False])

# Seleccionar las columnas de interés
df_bancos = df_bancos[['Empresa', 'Ingresos', 'Activos', 'Ganancias', 'Margen de Rentabilidad', 'Rentabilidad de los Activos (ROA)']]

# Filtrar las empresas con activos menores o iguales a $15,000 millones
df_bancos_small = df_bancos[df_bancos['Activos'] <= 15000]

# Crear la gráfica original
plt.figure(figsize=(15,8))
sns.set_style("whitegrid")
sns.set_palette("husl")
ax = sns.scatterplot(x='Ingresos', y='Ganancias', size='Activos', hue='Rentabilidad de los Activos (ROA)', sizes=(50, 500), data=df_bancos)

# Resaltar las empresas con activos menores o iguales a $15,000 millones
sns.scatterplot(x='Ingresos', y='Ganancias', size='Activos', hue='Rentabilidad de los Activos (ROA)', sizes=(50, 500), data=df_bancos_small, marker='s', edgecolor='black', linewidth=1, ax=ax)

# Añadir los nombres de las empresas debajo de los puntos
for i in range(len(df_bancos_small)):
    plt.annotate(df_bancos_small.iloc[i]['Empresa'] + '\nU${:,.0f}'.format(df_bancos_small.iloc[i]['Activos']),
                 xy=(df_bancos_small.iloc[i]['Ingresos'], df_bancos_small.iloc[i]['Ganancias']),
                 xytext=(df_bancos_small.iloc[i]['Ingresos']+50000, df_bancos_small.iloc[i]['Ganancias']+50000),
                 fontsize=10, ha='center', va='center', weight='bold', color='black',
                 arrowprops=dict(facecolor='black', arrowstyle='wedge,tail_width=0.5', connectionstyle='arc3,rad=0.5', mutation_scale=20))

# Crear la leyenda personalizada
roa_labels = ['0.0%', '1%', '5%']
roa_colors = ['#d5bfba', '#976588', '#3f334c']
handles = [plt.scatter([], [], s=100, marker='o', color=roa_colors[i]) for i in range(3)]
plt.legend(handles, roa_labels, title='Rentabilidad de los Activos (ROA)', fontsize=12, title_fontsize=14)

# Agregar título y subtítulo
plt.title('Ganancias, ingresos y activos para los años entre 2015-2022', fontsize=20)
plt.suptitle('Agrupados por Rentabilidad de los Activos (ROA)', fontsize=16, y=0.95)

# Agregar etiquetas de los ejes con separador de miles
ax.xaxis.set_major_formatter(mtick.StrMethodFormatter('{x:,.0f}'))
ax.yaxis.set_major_formatter(mtick.StrMethodFormatter('{x:,.0f}'))
plt.xlabel('Ingresos (millones de dólares)', fontsize=14)
plt.ylabel('Ganancias (millones de dólares)', fontsize=14)

# Cambiar tamaño de fuente y los ejes
plt.xticks(fontsize=12)
plt.yticks(fontsize=12)
plt.tick_params(axis='both', which='both', length=0)

plt.show()
```

![png](Data_Insider_files/Data_Insider_118_0.png)

###H. ¿Cuáles fueron las ganancias anuales de las principales empresas en la Industria automotriz?

```python
import pandas as pd

# Filtrar las empresas de la industria Transportation
df_automotriz = df_2015_2022[df_2015_2022['Industria'] == 'transportation']

# Agrupar por empresa, año y sumar las ganancias
ganancias_anuales = df_automotriz.groupby(['Empresa', 'Año'])['Ganancias'].sum().reset_index()

# Agrupar por empresa y sumar las ganancias totales
ganancias_totales = ganancias_anuales.groupby('Empresa')['Ganancias'].sum().reset_index()

# Renombrar la columna de ganancias totales
ganancias_totales = ganancias_totales.rename(columns={'Ganancias': 'Ganancias Totales'})

# Unir los DataFrames de ganancias anuales y ganancias totales
df_ganancias = pd.merge(ganancias_anuales, ganancias_totales, on='Empresa')

# Mostrar el DataFrame resultante
df_ganancias
```

  <div id="df-1d213e59-5897-48a9-a285-53c0af147b24">
    <div class="colab-df-container">
      <div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }

</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Empresa</th>
      <th>Año</th>
      <th>Ganancias</th>
      <th>Ganancias Totales</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>american airlines group</td>
      <td>2019</td>
      <td>1412.0</td>
      <td>-1706.0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>american airlines group</td>
      <td>2020</td>
      <td>-740.0</td>
      <td>-1706.0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>american airlines group</td>
      <td>2022</td>
      <td>-2378.0</td>
      <td>-1706.0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>cosco shipping</td>
      <td>2020</td>
      <td>-13.5</td>
      <td>15300.0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>cosco shipping</td>
      <td>2021</td>
      <td>1458.6</td>
      <td>15300.0</td>
    </tr>
    <tr>
      <th>5</th>
      <td>cosco shipping</td>
      <td>2022</td>
      <td>13854.9</td>
      <td>15300.0</td>
    </tr>
    <tr>
      <th>6</th>
      <td>delta air lines</td>
      <td>2019</td>
      <td>4086.0</td>
      <td>8105.0</td>
    </tr>
    <tr>
      <th>7</th>
      <td>delta air lines</td>
      <td>2020</td>
      <td>3503.0</td>
      <td>8105.0</td>
    </tr>
    <tr>
      <th>8</th>
      <td>delta air lines</td>
      <td>2022</td>
      <td>516.0</td>
      <td>8105.0</td>
    </tr>
    <tr>
      <th>9</th>
      <td>east japan railway</td>
      <td>2015</td>
      <td>1901.7</td>
      <td>13211.1</td>
    </tr>
    <tr>
      <th>10</th>
      <td>east japan railway</td>
      <td>2016</td>
      <td>1922.2</td>
      <td>13211.1</td>
    </tr>
    <tr>
      <th>11</th>
      <td>east japan railway</td>
      <td>2017</td>
      <td>2303.0</td>
      <td>13211.1</td>
    </tr>
    <tr>
      <th>12</th>
      <td>east japan railway</td>
      <td>2018</td>
      <td>2607.2</td>
      <td>13211.1</td>
    </tr>
    <tr>
      <th>13</th>
      <td>east japan railway</td>
      <td>2019</td>
      <td>2652.0</td>
      <td>13211.1</td>
    </tr>
    <tr>
      <th>14</th>
      <td>east japan railway</td>
      <td>2020</td>
      <td>1825.0</td>
      <td>13211.1</td>
    </tr>
    <tr>
      <th>15</th>
      <td>fedex</td>
      <td>2019</td>
      <td>3630.0</td>
      <td>11429.0</td>
    </tr>
    <tr>
      <th>16</th>
      <td>fedex</td>
      <td>2020</td>
      <td>-350.0</td>
      <td>11429.0</td>
    </tr>
    <tr>
      <th>17</th>
      <td>fedex</td>
      <td>2021</td>
      <td>3023.0</td>
      <td>11429.0</td>
    </tr>
    <tr>
      <th>18</th>
      <td>fedex</td>
      <td>2022</td>
      <td>5126.0</td>
      <td>11429.0</td>
    </tr>
    <tr>
      <th>19</th>
      <td>union pacific</td>
      <td>2015</td>
      <td>5180.0</td>
      <td>9780.0</td>
    </tr>
    <tr>
      <th>20</th>
      <td>union pacific</td>
      <td>2016</td>
      <td>4600.0</td>
      <td>9780.0</td>
    </tr>
    <tr>
      <th>21</th>
      <td>united airlines holdings</td>
      <td>2019</td>
      <td>2274.0</td>
      <td>3287.0</td>
    </tr>
    <tr>
      <th>22</th>
      <td>united airlines holdings</td>
      <td>2020</td>
      <td>1013.0</td>
      <td>3287.0</td>
    </tr>
    <tr>
      <th>23</th>
      <td>united parcel service</td>
      <td>2019</td>
      <td>4791.0</td>
      <td>4791.0</td>
    </tr>
  </tbody>
</table>
</div>
      <button class="colab-df-convert" onclick="convertToInteractive('df-1d213e59-5897-48a9-a285-53c0af147b24')"
              title="Convert this dataframe to an interactive table."
              style="display:none;">

<svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
width="24px">
<path d="M0 0h24v24H0V0z" fill="none"/>
<path d="M18.56 5.44l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94zm-11 1L8.5 8.5l.94-2.06 2.06-.94-2.06-.94L8.5 2.5l-.94 2.06-2.06.94zm10 10l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94z"/><path d="M17.41 7.96l-1.37-1.37c-.4-.4-.92-.59-1.43-.59-.52 0-1.04.2-1.43.59L10.3 9.45l-7.72 7.72c-.78.78-.78 2.05 0 2.83L4 21.41c.39.39.9.59 1.41.59.51 0 1.02-.2 1.41-.59l7.78-7.78 2.81-2.81c.8-.78.8-2.07 0-2.86zM5.41 20L4 18.59l7.72-7.72 1.47 1.35L5.41 20z"/>
</svg>
</button>

  <style>
    .colab-df-container {
      display:flex;
      flex-wrap:wrap;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

      <script>
        const buttonEl =
          document.querySelector('#df-1d213e59-5897-48a9-a285-53c0af147b24 button.colab-df-convert');
        buttonEl.style.display =
          google.colab.kernel.accessAllowed ? 'block' : 'none';

        async function convertToInteractive(key) {
          const element = document.querySelector('#df-1d213e59-5897-48a9-a285-53c0af147b24');
          const dataTable =
            await google.colab.kernel.invokeFunction('convertToInteractive',
                                                     [key], {});
          if (!dataTable) return;

          const docLinkHtml = 'Like what you see? Visit the ' +
            '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
            + ' to learn more about interactive tables.';
          element.innerHTML = '';
          dataTable['output_type'] = 'display_data';
          await google.colab.output.renderOutput(dataTable, element);
          const docLink = document.createElement('div');
          docLink.innerHTML = docLinkHtml;
          element.appendChild(docLink);
        }
      </script>
    </div>

  </div>

```python
import seaborn as sns
import matplotlib.pyplot as plt

# Filtrar las empresas de la industria Transportation
df_automotriz = df_2015_2022[df_2015_2022['Industria'] == 'transportation']

# Agrupar por empresa, año y sumar las ganancias
ganancias_anuales = df_automotriz.groupby(['Empresa', 'Año'])['Ganancias'].sum().reset_index()

# Agrupar por empresa y sumar las ganancias totales
ganancias_totales = ganancias_anuales.groupby('Empresa')['Ganancias'].sum().reset_index()

# Renombrar la columna de ganancias totales
ganancias_totales = ganancias_totales.rename(columns={'Ganancias': 'Ganancias Totales'})

# Unir los DataFrames de ganancias anuales y ganancias totales
df_ganancias = pd.merge(ganancias_anuales, ganancias_totales, on='Empresa')

# Crear una gráfica para cada empresa
num_empresas = len(ganancias_totales)
num_filas = num_empresas // 4 + (num_empresas % 4 > 0)
fig, axs = plt.subplots(nrows=num_filas, ncols=4, figsize=(20, 5*num_filas))
sns.set_palette('pastel')

for i, empresa in enumerate(ganancias_totales['Empresa']):
    # Filtrar el DataFrame para la empresa actual
    df_empresa = df_ganancias[df_ganancias['Empresa'] == empresa]

    # Obtener la ganancia total de la empresa
    ganancia_total = df_empresa.iloc[0]['Ganancias Totales']

    # Obtener los índices de la fila y columna actual
    row = i // 4
    col = i % 4

    # Crear la gráfica de barras
    ax = sns.barplot(x='Año', y='Ganancias', data=df_empresa, ax=axs[row][col])

    # Agregar línea horizontal para la ganancia total
    ax.axhline(y=ganancia_total, color='r', linestyle='--')

    # Agregar título y subtítulo
    ax.set_title(f'{empresa} / año')
    ax.set_xlabel('Año')
    ax.set_ylabel('Ganancias')

    # Ajustar los límites del eje y para que se ajusten a los datos
    ymin, ymax = ax.get_ylim()
    if ymin < 0:
        ax.set_ylim(ymin * 1.1, ymax * 1.1)

    # Agregar leyenda solo a la última gráfica de cada fila
    if col == 3:
        ax.axhline(y=ganancia_total, color='r', linestyle='--', label='Ganancias Totales')
        ax.legend()

# Añadir título universal
fig.suptitle('Ganancias anuales de las principales empresas en la Industria automotriz', fontsize=16)

# Ajustar el espaciado entre las gráficas y mostrar la figura
plt.tight_layout()
plt.show()
```

![png](Data_Insider_files/Data_Insider_121_0.png)

#6. Visualización de datos

##¡Extra!

###A.Crea un gráfico de carrera de barras (racing bar chart) que indique la variación del valor de mercado por industria durante el periodo 2015 - 2022. Utiliza el repositorio [Bar Chart Race](https://github.com/dexplo/bar_chart_race/) para que utilices esta sencilla herramienta.

```python
# !apt-get install -y ffmpeg

# !pip install bar_chart_race
```

```python
# import pandas as pd
# import bar_chart_race as bcr

# # Seleccionar solo las columnas relevantes
# df_ganancias = df_2015_2022[['Industria', 'Año', 'Valor de Mercado']]

# # Ordenar los datos por año y valor de mercado
# df_ganancias = df_ganancias.sort_values(['Año', 'Valor de Mercado'], ascending=[True, False])

# # Crear el gráfico de carrera de barras
# bcr.bar_chart_race(df=df_ganancias,
#                    title='Variación del valor de mercado por industria (2015-2022)',
#                    orientation='h',
#                    sort='desc',
#                    n_bars=6,
#                    fixed_order=False,
#                    steps_per_period=10,
#                    period_length=500)
```

```python
import pandas as pd
import matplotlib.pyplot as plt
from matplotlib.animation import FuncAnimation
from IPython.display import HTML

# Leer los datos y filtrar los de 2015 a 2022
df_ganancias = df_2015_2022.loc[(df_2015_2022['Año'] >= '2015') & (df_2015_2022['Año'] <= '2022')]

# Agrupar los datos por industria y seleccionar la empresa con mayor valor de mercado en cada grupo
df_top1 = df_ganancias.groupby('Industria').apply(lambda x: x.loc[x['Valor de Mercado'].idxmax()])

# Ordenar los datos por valor de mercado y seleccionar las 6 mejores industrias
df_top6 = df_top1.sort_values('Valor de Mercado', ascending=False).head(6)

# Crear la figura y el eje
fig, ax = plt.subplots(figsize=(8, 6))
fig.set_size_inches(30, 6, forward=True)
fig.subplots_adjust(right=0.85) # Agregar un padding al lado derecho del gráfico

# Definir la función update
def update(year):
    # Filtrar los datos para el año actual y las 6 mejores industrias
    df_filtered = df_ganancias.loc[(df_ganancias['Año'] == str(year)) & (df_ganancias['Industria'].isin(df_top6['Industria']))]

    # Seleccionar la empresa con mayor valor de mercado por industria para cada año
    df_year = df_filtered.loc[df_filtered.groupby('Industria')['Valor de Mercado'].idxmax()]

    # Crear el gráfico de barras
    ax.clear()
    bars = ax.barh(df_year['Industria'], df_year['Valor de Mercado'], color=['#2CA02C', '#FF7F0E', '#1F77B4', '#D62728', '#9467BD', '#8c564b'], label='Valor de mercado')

    # Agregar etiquetas a las barras
    for bar, label in zip(bars, df_year['Empresa']):
        ax.annotate(label, xy=(bar.get_x() + bar.get_width() / 2, bar.get_y() + bar.get_height() / 2), ha='center', va='center', fontsize=12, color='white')
        bar.set_label(label)

    # Agregar el título y los ejes
    ax.set_title(f'Las 6 mejores Industrias por Empresa con mayor Valor de Mercado ({year})', fontsize=20)
    ax.set_xlabel('Valor de mercado (en millones de dólares)', fontsize=14)
    ax.set_ylabel('Industria', fontsize=14)
    ax.tick_params(labelsize=12)
    ax.invert_yaxis()

    # Formatear los valores del mercado
    ax.get_xaxis().set_major_formatter(plt.FuncFormatter(lambda x, loc: f'U${x/1000000:.1f}M'))

    # Crear la leyenda
    ax.legend(bbox_to_anchor=(1.05, 1), loc='upper left', ncol=1, fontsize=12)

# Crear la animación
anim = FuncAnimation(fig, update, frames=range(2015, 2023), interval=5000, repeat=True)

# Exportar la animación a un archivo de video
# anim.save('grafico.mp4', dpi=150)

# Convertir la animación a HTML5 y mostrarla en Colab
html5_video = anim.to_html5_video()
HTML(html5_video)
```

<video width="3000" height="600" controls autoplay loop>
  <source type="video/mp4" src="data:video/mp4;base64,AAAAHGZ0eXBNNFYgAAACAGlzb21pc28yYXZjMQAAAAhmcmVlAAHVNm1kYXQAAAKtBgX//6ncRem9
5tlIt5Ys2CDZI+7veDI2NCAtIGNvcmUgMTU1IHIyOTE3IDBhODRkOTggLSBILjI2NC9NUEVHLTQg
QVZDIGNvZGVjIC0gQ29weWxlZnQgMjAwMy0yMDE4IC0gaHR0cDovL3d3dy52aWRlb2xhbi5vcmcv
eDI2NC5odG1sIC0gb3B0aW9uczogY2FiYWM9MSByZWY9MyBkZWJsb2NrPTE6MDowIGFuYWx5c2U9
MHgzOjB4MTEzIG1lPWhleCBzdWJtZT03IHBzeT0xIHBzeV9yZD0xLjAwOjAuMDAgbWl4ZWRfcmVm
PTEgbWVfcmFuZ2U9MTYgY2hyb21hX21lPTEgdHJlbGxpcz0xIDh4OGRjdD0xIGNxbT0wIGRlYWR6
b25lPTIxLDExIGZhc3RfcHNraXA9MSBjaHJvbWFfcXBfb2Zmc2V0PS0yIHRocmVhZHM9MyBsb29r
YWhlYWRfdGhyZWFkcz0xIHNsaWNlZF90aHJlYWRzPTAgbnI9MCBkZWNpbWF0ZT0xIGludGVybGFj
ZWQ9MCBibHVyYXlfY29tcGF0PTAgY29uc3RyYWluZWRfaW50cmE9MCBiZnJhbWVzPTMgYl9weXJh
bWlkPTIgYl9hZGFwdD0xIGJfYmlhcz0wIGRpcmVjdD0xIHdlaWdodGI9MSBvcGVuX2dvcD0wIHdl
aWdodHA9MiBrZXlpbnQ9MjUwIGtleWludF9taW49MSBzY2VuZWN1dD00MCBpbnRyYV9yZWZyZXNo
PTAgcmNfbG9va2FoZWFkPTQwIHJjPWNyZiBtYnRyZWU9MSBjcmY9MjMuMCBxY29tcD0wLjYwIHFw
bWluPTAgcXBtYXg9NjkgcXBzdGVwPTQgaXBfcmF0aW89MS40MCBhcT0xOjEuMDAAgAAAtVlliIQA
F//+99S3zLLtU2+2C6j3op4mX0N1JQGblsTtOoAAAAMAAAMAAAMAAAMAAAMAACrtg8NJfsa2aeEg
AAADAAADAAADAAfwAOI//4Gk3/MAVNYU5cnl8cm1yDX3vuyblP/4QZ++FS8fEK2FI2GA9ghx/OS+
IpjnVYf7JCATEOXR52jOxsZkhkaLd4e20P1KwV2FT4QKSlvoSRs5Vxu6fkEtI3Yn5rh9uTyD14/c
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
YXRhAAAAAQAAAABMYXZmNTguMjkuMTAw
">
  Your browser does not support the video tag.
</video>

![png](Data_Insider_files/Data_Insider_127_1.png)

###B.Crea otro gráfico de carrera de barras que muestre la variación del número de empleados por industria durante el periodo 2015 - 2022.

```python
import pandas as pd

# Leer los datos y filtrar por la industria deseada
df_industria = df_2015_2022[df_2015_2022['Industria'] == 'retailing']

# Agrupar los datos por año y sumar los empleados de la industria
df_empleados = df_industria.groupby('Año')['Empleados'].sum().reset_index()

# Mostrar el número de empleados por año
print(df_empleados)
```

        Año  Empleados
    0  2015    1639586
    1  2016    2410036
    2  2017    2597109
    3  2018    4895823
    4  2019    4803267
    5  2020    5492541
    6  2021    5997078
    7  2022    6001421

```python
# !pip install ffmpeg-python

# !pip install bar_chart_race
```

```python
# import pandas as pd
# import bar_chart_race as bcr

# df_empleados = df_2015_2022.loc[(df_2015_2022['Año'] >= '2015') & (df_2015_2022['Año'] <= '2022')]

# df_grouped = df_empleados.groupby(['Industria', 'Año'])['Empleados'].sum().reset_index()

# bcr.bar_chart_race(
#     df=df_grouped,
#     title='Variación del número de empleados por industria',
#     orientation='h',
#     sort='desc',
#     n_bars=6,
#     fixed_order=False,
#     steps_per_period=10,
#     period_length=500,
#     interpolate_period=False,
#     label_bars=True,
#     bar_size=.95,
#     period_label={'x': .99, 'y': .25, 'ha': 'right', 'va': 'center'},
#     period_fmt='%Y',
#     period_summary_func=lambda v, r: {'x': .99, 'y': .18, 's': f'Total empleados: {v.sum():,.0f}', 'ha': 'right', 'size': 8, 'family': 'Courier New'},
#     perpendicular_bar_func='median',
#     figsize=(6.5, 3.5),
#     dpi=144,
#     cmap='dark12',
#     title_size='',
#     bar_label_size=7,
#     tick_label_size=7,
#     shared_fontdict={'family' : 'Helvetica', 'color' : '.1'},
#     scale='linear',
#     writer=None,
#     fig=None,
#     bar_kwargs={'alpha': .7},
#     filter_column_colors=False)
```

```python
import pandas as pd
import matplotlib.pyplot as plt
from matplotlib.animation import FuncAnimation
from IPython.display import HTML

# Leer los datos y filtrar los de 2015 a 2022
df_empleados = df_2015_2022.loc[(df_2015_2022['Año'] >= '2015') & (df_2015_2022['Año'] <= '2022')]

# Agrupar los datos por año e industria y sumar los empleados de cada empresa
df_year_industrias = df_empleados.groupby(['Año', 'Industria']).agg({'Empleados': sum}).reset_index()

# Seleccionar todas las industrias
industrias = df_year_industrias['Industria'].unique()

# Crear la figura y el eje
fig, ax = plt.subplots(figsize=(25, 30))
fig.subplots_adjust(right=0.85) # Agregar un padding al lado derecho del gráfico

# Definir la función update
def update(year):
    # Filtrar los datos para el año actual y todas las industrias
    df_filtered = df_year_industrias.loc[(df_year_industrias['Año'] == str(year)) & (df_year_industrias['Industria'].isin(industrias))]

    # Ordenar las industrias por cantidad de empleados
    df_filtered = df_filtered.sort_values('Empleados', ascending=False)

    # Crear el gráfico de barras
    ax.clear()
    cmap = plt.get_cmap('tab20c') # Obtener la paleta de colores
    colors = cmap(range(len(industrias))) # Asignar un color a cada industria
    bars = ax.bar(df_filtered['Industria'], df_filtered['Empleados'], color=colors, width=0.8, align='center', edgecolor='white')

    # Agregar el título y los ejes
    ax.set_title(f'Todas las Industrias con cantidad de Empleados ({year})', fontsize=20)
    ax.set_xlabel('Industria', fontsize=14)
    ax.set_ylabel('Cantidad de empleados (en millones)', fontsize=14)
    ax.tick_params(labelsize=12, axis='x', rotation=90)

    # Formatear los valores de empleados
    ax.get_yaxis().set_major_formatter(plt.FuncFormatter(lambda x, loc: f'{x/1000000:,.1f}M'))

    # Agregar el total de empleados encima de cada barra
    for bar, empleados in zip(bars, df_filtered['Empleados']):
        ax.text(bar.get_x() + bar.get_width() / 2, bar.get_height() + 50000, f'{empleados/1000000:,.2f}M', ha='center', va='bottom', fontsize=10)

# Crear la animación
anim_b = FuncAnimation(fig, update, frames=range(2015, 2023), interval=5000, repeat=True)

# Exportar la animación a un archivo de video
#anim_b.save('grafico_b.mp4', dpi=150)

# Convertir la animación a HTML5 y mostrarla en Colab
html5_video = anim_b.to_html5_video()
HTML(html5_video)
```

<video width="2500" height="3000" controls autoplay loop>
  <source type="video/mp4" src="data:video/mp4;base64,AAAAHGZ0eXBNNFYgAAACAGlzb21pc28yYXZjMQAAAAhmcmVlAARyM21kYXQAAAKtBgX//6ncRem9
5tlIt5Ys2CDZI+7veDI2NCAtIGNvcmUgMTU1IHIyOTE3IDBhODRkOTggLSBILjI2NC9NUEVHLTQg
QVZDIGNvZGVjIC0gQ29weWxlZnQgMjAwMy0yMDE4IC0gaHR0cDovL3d3dy52aWRlb2xhbi5vcmcv
eDI2NC5odG1sIC0gb3B0aW9uczogY2FiYWM9MSByZWY9MyBkZWJsb2NrPTE6MDowIGFuYWx5c2U9
MHgzOjB4MTEzIG1lPWhleCBzdWJtZT03IHBzeT0xIHBzeV9yZD0xLjAwOjAuMDAgbWl4ZWRfcmVm
PTEgbWVfcmFuZ2U9MTYgY2hyb21hX21lPTEgdHJlbGxpcz0xIDh4OGRjdD0xIGNxbT0wIGRlYWR6
b25lPTIxLDExIGZhc3RfcHNraXA9MSBjaHJvbWFfcXBfb2Zmc2V0PS0yIHRocmVhZHM9MyBsb29r
YWhlYWRfdGhyZWFkcz0xIHNsaWNlZF90aHJlYWRzPTAgbnI9MCBkZWNpbWF0ZT0xIGludGVybGFj
ZWQ9MCBibHVyYXlfY29tcGF0PTAgY29uc3RyYWluZWRfaW50cmE9MCBiZnJhbWVzPTMgYl9weXJh
bWlkPTIgYl9hZGFwdD0xIGJfYmlhcz0wIGRpcmVjdD0xIHdlaWdodGI9MSBvcGVuX2dvcD0wIHdl
aWdodHA9MiBrZXlpbnQ9MjUwIGtleWludF9taW49MSBzY2VuZWN1dD00MCBpbnRyYV9yZWZyZXNo
PTAgcmNfbG9va2FoZWFkPTQwIHJjPWNyZiBtYnRyZWU9MSBjcmY9MjMuMCBxY29tcD0wLjYwIHFw
bWluPTAgcXBtYXg9NjkgcXBzdGVwPTQgaXBfcmF0aW89MS40MCBhcT0xOjEuMDAAgAAA/ZVliIQA
F//+99S3zLLtU2+2C6j3op4mX0N1JQGblsTtOoAAAAMAAAMAAAMAAAMAAAMAI/CVbHMgxrZp4SAA
AAMAAAMAAAa0AAADAABmQAAAAwAOMAAAAwADYAAAAwABLAAAAwAAX4AAAAMALcAAAAMAHEAAAAMA
DYAAAAMAB4gAAAMABDQAAAMAA2gAAAMAAlgAAAMAAdgAAAMAAAMAAAMAAAMAAAMAAAMAAAMAAAMA
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
YXRhAAAAAQAAAABMYXZmNTguMjkuMTAw
">
  Your browser does not support the video tag.
</video>

![png](Data_Insider_files/Data_Insider_132_1.png)

###C.Utilizando la biblioteca [Choropleth Maps in Python](https://plotly.com/python/choropleth-maps/#using-geopandas-data-frames), genera un mapa con el total de ventas globales por país en el año 2020

```python
import pandas as pd

# Agrupar por pais y sumar las ganancias totales
ventas_totales = df_2015_2022.groupby('Pais')['Ganancias'].sum().reset_index()

# Renombrar la columna de ganancias totales
df_ventas_globales = ventas_totales.rename(columns={'Ganancias': 'Ventas Globales'})

# Mostrar el DataFrame resultante
df_ventas_globales
```

  <div id="df-4c25dd28-1cab-49c9-bdb1-46dc67ea8a25">
    <div class="colab-df-container">
      <div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }

</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Pais</th>
      <th>Ventas Globales</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Australia</td>
      <td>96799.4</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Austria</td>
      <td>5283.9</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Belgium</td>
      <td>45312.0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Bermuda</td>
      <td>6057.0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Brazil</td>
      <td>137511.9</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Canada</td>
      <td>196369.3</td>
    </tr>
    <tr>
      <th>6</th>
      <td>Chile</td>
      <td>502.8</td>
    </tr>
    <tr>
      <th>7</th>
      <td>China</td>
      <td>1482651.2</td>
    </tr>
    <tr>
      <th>8</th>
      <td>Colombia</td>
      <td>3751.6</td>
    </tr>
    <tr>
      <th>9</th>
      <td>Finland</td>
      <td>-1969.2</td>
    </tr>
    <tr>
      <th>10</th>
      <td>France</td>
      <td>320223.6</td>
    </tr>
    <tr>
      <th>11</th>
      <td>Germany</td>
      <td>409937.4</td>
    </tr>
    <tr>
      <th>12</th>
      <td>Hong Kong</td>
      <td>58422.0</td>
    </tr>
    <tr>
      <th>13</th>
      <td>India</td>
      <td>111164.2</td>
    </tr>
    <tr>
      <th>14</th>
      <td>Ireland</td>
      <td>74911.9</td>
    </tr>
    <tr>
      <th>15</th>
      <td>Italy</td>
      <td>62288.0</td>
    </tr>
    <tr>
      <th>16</th>
      <td>Japan</td>
      <td>700160.8</td>
    </tr>
    <tr>
      <th>17</th>
      <td>Luxembourg</td>
      <td>13966.3</td>
    </tr>
    <tr>
      <th>18</th>
      <td>Mexico</td>
      <td>4537.9</td>
    </tr>
    <tr>
      <th>19</th>
      <td>Netherlands</td>
      <td>184866.0</td>
    </tr>
    <tr>
      <th>20</th>
      <td>Norway</td>
      <td>13377.3</td>
    </tr>
    <tr>
      <th>21</th>
      <td>Russia</td>
      <td>254933.9</td>
    </tr>
    <tr>
      <th>22</th>
      <td>Singapore</td>
      <td>12746.0</td>
    </tr>
    <tr>
      <th>23</th>
      <td>South Korea</td>
      <td>350206.2</td>
    </tr>
    <tr>
      <th>24</th>
      <td>Spain</td>
      <td>96121.5</td>
    </tr>
    <tr>
      <th>25</th>
      <td>Sweden</td>
      <td>570.0</td>
    </tr>
    <tr>
      <th>26</th>
      <td>Switzerland</td>
      <td>208400.9</td>
    </tr>
    <tr>
      <th>27</th>
      <td>Taiwan</td>
      <td>79703.5</td>
    </tr>
    <tr>
      <th>28</th>
      <td>Thailand</td>
      <td>6613.0</td>
    </tr>
    <tr>
      <th>29</th>
      <td>Turkey</td>
      <td>4980.4</td>
    </tr>
    <tr>
      <th>30</th>
      <td>United Kingdom</td>
      <td>401189.7</td>
    </tr>
    <tr>
      <th>31</th>
      <td>United States</td>
      <td>5159154.3</td>
    </tr>
    <tr>
      <th>32</th>
      <td>Venezuela</td>
      <td>3553.4</td>
    </tr>
  </tbody>
</table>
</div>
      <button class="colab-df-convert" onclick="convertToInteractive('df-4c25dd28-1cab-49c9-bdb1-46dc67ea8a25')"
              title="Convert this dataframe to an interactive table."
              style="display:none;">

<svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
width="24px">
<path d="M0 0h24v24H0V0z" fill="none"/>
<path d="M18.56 5.44l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94zm-11 1L8.5 8.5l.94-2.06 2.06-.94-2.06-.94L8.5 2.5l-.94 2.06-2.06.94zm10 10l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94z"/><path d="M17.41 7.96l-1.37-1.37c-.4-.4-.92-.59-1.43-.59-.52 0-1.04.2-1.43.59L10.3 9.45l-7.72 7.72c-.78.78-.78 2.05 0 2.83L4 21.41c.39.39.9.59 1.41.59.51 0 1.02-.2 1.41-.59l7.78-7.78 2.81-2.81c.8-.78.8-2.07 0-2.86zM5.41 20L4 18.59l7.72-7.72 1.47 1.35L5.41 20z"/>
</svg>
</button>

  <style>
    .colab-df-container {
      display:flex;
      flex-wrap:wrap;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

      <script>
        const buttonEl =
          document.querySelector('#df-4c25dd28-1cab-49c9-bdb1-46dc67ea8a25 button.colab-df-convert');
        buttonEl.style.display =
          google.colab.kernel.accessAllowed ? 'block' : 'none';

        async function convertToInteractive(key) {
          const element = document.querySelector('#df-4c25dd28-1cab-49c9-bdb1-46dc67ea8a25');
          const dataTable =
            await google.colab.kernel.invokeFunction('convertToInteractive',
                                                     [key], {});
          if (!dataTable) return;

          const docLinkHtml = 'Like what you see? Visit the ' +
            '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
            + ' to learn more about interactive tables.';
          element.innerHTML = '';
          dataTable['output_type'] = 'display_data';
          await google.colab.output.renderOutput(dataTable, element);
          const docLink = document.createElement('div');
          docLink.innerHTML = docLinkHtml;
          element.appendChild(docLink);
        }
      </script>
    </div>

  </div>

```python
import pandas as pd
import plotly.express as px
import json
import requests

# Agrupar por país y sumar las ganancias totales
ventas_totales = df_2015_2022.groupby('Pais')['Ganancias'].sum().reset_index()

# Renombrar la columna de ganancias totales
df_ventas_globales = ventas_totales.rename(columns={'Ganancias': 'Ventas Globales'})

# Obtener el archivo GeoJSON desde el repositorio de GitHub
url = 'https://raw.githubusercontent.com/johan/world.geo.json/master/countries.geo.json'
geojson = requests.get(url).json()

# Crear el mapa de coropletas
fig = px.choropleth(df_ventas_globales, locations='Pais', locationmode='country names', color='Ventas Globales',
                    featureidkey='properties.name', geojson=geojson,
                    color_continuous_scale='Viridis', range_color=(0, df_ventas_globales['Ventas Globales'].max()),
                    title='Ventas Globales por País')

# Configurar el tamaño y el diseño del mapa y los datos de herramientas emergentes (hover)
fig.update_layout(height=600, margin={"r":0,"l":0,"b":0},
                  coloraxis_colorbar=dict(title='Ventas Globales (en millones de dólares)',
                                          tickprefix='U$', separatethousands=True),
                  geo=dict(showcountries=True, showcoastlines=True, projection_type='equirectangular',
                           landcolor='rgb(211, 211, 211)', countrycolor='black'))

# Actualizar las opciones de las herramientas emergentes (hover)
fig.update_traces(hovertemplate='<b>%{location}</b><br><br>Ventas Globales: U$%{z:,.1f}')

# Mostrar el mapa
fig.show()
```

![png](Data_Insider_files/Data_Insider_133.png)

[Ventas Globales por País "CLICK AQUI PARA VER EN FORMA INTERACTIVA"](https://datainsider.pages.dev/)

<html>
<head><meta charset="utf-8" /></head>
<body>
    <div>            <script src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.5/MathJax.js?config=TeX-AMS-MML_SVG"></script><script type="text/javascript">if (window.MathJax && window.MathJax.Hub && window.MathJax.Hub.Config) {window.MathJax.Hub.Config({SVG: {font: "STIX-Web"}});}</script>                <script type="text/javascript">window.PlotlyConfig = {MathJaxConfig: 'local'};</script>

var gd = document.getElementById('1b7a2911-1fee-4638-ab6c-899d771c192e');
var x = new MutationObserver(function (mutations, observer) {{
        var display = window.getComputedStyle(gd).display;
        if (!display || display === 'none') {{
            console.log([gd, 'removed!']);
            Plotly.purge(gd);
            observer.disconnect();
        }}
}});

// Listen for the removal of the full notebook cells
var notebookContainer = gd.closest('#notebook-container');
if (notebookContainer) {{
    x.observe(notebookContainer, {childList: true});
}}

// Listen for the clearing of the current output cell
var outputEl = gd.closest('.output');
if (outputEl) {{
    x.observe(outputEl, {childList: true});
}}

                        })                };                            </script>        </div>

</body>
</html>

#README

```python
!pip install nbconvert
```

```python
!jupyter nbconvert --to markdown Robot_Trading.ipynb
```