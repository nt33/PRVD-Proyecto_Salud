# Proyecto: Análisis territorial de población y centros sanitarios en la Comunitat Valenciana

## Descripción general

Este proyecto tiene como objetivo realizar un **análisis estadístico y territorial** de la población y la distribución de los centros sanitarios en la Comunitat Valenciana, a partir de la integración de múltiples fuentes de datos oficiales.

Se combinan datos demográficos a nivel municipal con información geoespacial sobre delimitaciones territoriales y localización de centros sanitarios, con el fin de estudiar la **relación entre la distribución de la población y la oferta de recursos sanitarios** en el territorio.

## Fuentes de datos

El proyecto se basa en las siguientes fuentes principales:

- **Instituto Nacional de Estadística (INE)**  
  [Datos de población por municipio, desagregados por grupo de edad, sexo, nacionalidad y periodo temporal](https://www.ine.es/jaxiT3/Tabla.htm?t=68535)

- **Datos abiertos de la Generalitat Valenciana**  
   - [Delimitaciones municipales y comarcales de la Comunitat Valenciana](https://dadesobertes.gva.es/es/dataset/delimitacion-territorial-municipios-de-la-comunitat-valenciana)
   - [Sistema Valenciano de Salud – Centros sanitarios](https://dadesobertes.gva.es/es/dataset?q=centros+sanitarios+CV), a partir de la integración de:
      - Hospitales
      - Centros de especialidades
      - Centros de salud

## Objetivos del proyecto

Los principales objetivos del proyecto son:

- Preprocesar y limpiar los datos procedentes de distintas fuentes oficiales.
- Unir e integrar datasets demográficos, territoriales y sanitarios a nivel municipal.
- Analizar la distribución de la población en la Comunitat Valenciana según edad, sexo y nacionalidad.
- Estudiar la distribución territorial de los centros sanitarios.
- Relacionar la oferta de centros sanitarios con el tamaño y la estructura de la población.
- Identificar posibles desequilibrios territoriales en el acceso a recursos sanitarios.


## Metodología

El proyecto se estructura en varias fases:

1. **Preprocesado de datos**  
   Limpieza, filtrado y transformación individual de los datos demográficos, territoriales y sanitarios mediante notebooks independientes, generando conjuntos de datos procesados por fuente.

   En el caso de los centros sanitarios, se integran tres datasets del Sistema Valenciano de Salud (hospitales, centros de especialidades y centros de salud), que comparten estructura, codificación municipal y sistema de referencia espacial.

2. **Integración de fuentes**  
   Unión de los datasets previamente procesados a nivel municipal, utilizando identificadores geográficos comunes y verificando la coherencia territorial entre las distintas fuentes.

3. **Análisis estadístico y espacial**  
   Cálculo de indicadores (centros por habitante, población por grupo de edad, etc.) y representación cartográfica.

4. **Visualización de resultados**  
   Generación de mapas y gráficos que permitan interpretar los resultados obtenidos.

## Estructura del repositorio
```
├── data/
│   ├── raw/                # Datos originales (no incluidos)
│   ├── processed/          # Datos limpios por fuente (no incluidos)
│   └── integrated/         # Dataset final integrado (no incluido)
│
├── 01-preprocesado/
│   ├── datos_poblacion.ipynb
│   ├── datos_municipios.ipynb
│   └── datos_centros_sanitarios.ipynb
│
├── 02-integracion/
│   └── integracion_datasets.ipynb
│
├── 03-analisis/
│   └── analisis_descriptivo.ipynb
│
├── README.md
└── .gitignore
```

> ⚠️ Nota sobre los datos  
> Ninguna de las carpetas `data/*` se incluye en el repositorio de GitHub. Todos los archivos de datos están excluidos mediante `.gitignore` debido a su tamaño.  
> El repositorio contiene únicamente el código y los notebooks necesarios para reproducir el proceso de preprocesado, integración y análisis de los datos. La descarga de los conjuntos de datos originales se realiza manualmente siguiendo las instrucciones indicadas en este documento.



## Alcance

Este proyecto tiene un enfoque **exploratorio y descriptivo**, orientado al análisis de datos y visualización, y no pretende realizar inferencias causales ni evaluaciones clínicas.


## Descarga y generación de los datos

Este repositorio **no incluye ningún archivo de datos**, ni originales ni procesados. Para reproducir el proyecto es necesario descargar manualmente los conjuntos de datos originales y ejecutar los notebooks de preprocesado.

### 1. Descarga de datos originales

Los siguientes datasets deben descargarse y guardarse en la carpeta `data/raw/` con los nombres indicados:

1. **Datos de población (INE)**  
   Descargar los datos de población por municipio, grupo de edad, sexo y nacionalidad desde el INE y guardarlos como:  
   `data/raw/INE-poblacion-grupo-edad.csv`  
   Fuente: https://www.ine.es/jaxiT3/files/t/es/csv_bdsc/68535.csv

2. **Delimitaciones municipales (GVA)**  
   Descargar las delimitaciones municipales de la Comunitat Valenciana y guardarlas como:  
   `data/raw/GVA-municipios-delimitaciones.csv`  
   Fuente: https://terramapas.icv.gva.es/0105_Delimitaciones?request=GetFeature&service=WFS&version=2.0.0&typename=ICV.Municipios&outputformat=csv

3. **Centros sanitarios (Sistema Valenciano de Salud)**  
   Descargar los siguientes datasets y guardarlos en `data/raw/`:

   - **Hospitales**  
     `data/raw/GVA-hospitales.csv`  
     Fuente: https://dadesobertes.gva.es/es/dataset/sistema-valenciano-de-salud-centros-sanitarios-hospitales

   - **Centros de especialidades**  
     `data/raw/GVA-centros-de-especialidades.csv`  
     Fuente: https://dadesobertes.gva.es/es/dataset/sistema-valenciano-de-salud-centros-sanitarios-centros-de-especialidades4

   - **Centros de salud**  
     `data/raw/GVA-centros-de-salud.csv`  
     Fuente: https://dadesobertes.gva.es/es/dataset/sistema-valenciano-de-salud-centros-sanitarios-centros-de-salud


### 2. Generación de datos procesados e integrados

Una vez descargados los datos originales, se deben ejecutar los notebooks disponibles en la carpeta `01-preprocesado/`, que realizan el proceso de limpieza y transformación individual de cada fuente de datos. Posteriormente, la integración de las distintas fuentes se lleva a cabo mediante el notebook disponible en la carpeta `02-integracion/`.

Como resultado, se generan de forma local los datasets procesados por fuente en la carpeta `data/processed/` y el conjunto de datos final integrado en la carpeta `data/integrated/`. Estos archivos **no se versionan ni se suben al repositorio**.
