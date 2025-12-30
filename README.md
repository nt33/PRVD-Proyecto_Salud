# Proyecto: Análisis territorial de población y centros sanitarios en la Comunitat Valenciana

## Descripción general

Este proyecto tiene como objetivo realizar un **análisis estadístico y territorial** de la población y la distribución de los centros sanitarios en la Comunitat Valenciana, a partir de la integración de múltiples fuentes de datos oficiales.

Se combinan datos demográficos a nivel municipal con información geoespacial sobre delimitaciones territoriales y localización de centros sanitarios, con el fin de estudiar la **relación entre la distribución de la población y la oferta de recursos sanitarios** en el territorio.

## Fuentes de datos

El proyecto se basa en las siguientes fuentes principales:

- **Instituto Nacional de Estadística (INE)**  
  [Datos de población por municipio, desagregados por grupo de edad, sexo, nacionalidad y periodo temporal](https://www.ine.es/jaxiT3/Tabla.htm?t=68535&utm_source=chatgpt.com)

- **Datos abiertos de la Generalitat Valenciana**  
  - [Delimitaciones municipales y comarcales de la Comunitat Valenciana](https://dadesobertes.gva.es/es/dataset/delimitacion-territorial-municipios-de-la-comunitat-valenciana)
  - [Localización y características básicas de los centros sanitarios](https://datos.gob.es/es/catalogo/a10002983-registro-autonomico-de-centros-servicios-y-establecimientos-sanitarios-de-la-comunitat-valenciana)

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
   Limpieza, filtrado y transformación de los datos demográficos, territoriales y sanitarios mediante notebooks independientes.

2. **Integración de fuentes**  
   Unión de los datasets a nivel municipal utilizando identificadores geográficos comunes.

3. **Análisis estadístico y espacial**  
   Cálculo de indicadores (centros por habitante, población por grupo de edad, etc.) y representación cartográfica.

4. **Visualización de resultados**  
   Generación de mapas y gráficos que permitan interpretar los resultados obtenidos.

## Estructura del repositorio
```
├── data/
│ ├── raw/ # Datos originales descargados
│ ├── processed/ # Datos preprocesados
├── preprocesado/
│ ├── datos_poblacion.ipynb # Preprocesado datos INE
│ ├── datos_municipios.ipynb # Municipios y comarcas
│ └── datos_centros_sanitorios.ipynb # Centros sanitarios
├── README.md
```

## Alcance

Este proyecto tiene un enfoque **exploratorio y descriptivo**, orientado al análisis de datos y visualización, y no pretende realizar inferencias causales ni evaluaciones clínicas.


## Descarga de datos

Para reproducir el proyecto es necesario descargar manualmente los siguientes conjuntos de datos y guardarlos en la carpeta `raw_data`:

1. **Datos de población (INE)**  
   Descargar los datos de población por municipio, grupo de edad, sexo y nacionalidad desde el INE y guardarlos como:  
   `raw_data/INE-poblacion-grupo-edad.csv`  
   Fuente: https://www.ine.es/jaxiT3/files/t/es/csv_bdsc/68535.csv

2. **Delimitaciones municipales (GVA)**  
   Descargar las delimitaciones municipales de la Comunitat Valenciana y guardarlas como:  
   `raw_data/GVA-municipios-delimitaciones.csv`  
   Fuente: https://terramapas.icv.gva.es/0105_Delimitaciones?request=GetFeature&service=WFS&version=2.0.0&typename=ICV.Municipios&outputformat=csv

3. **Centros sanitarios (GVA – Banco de Datos)**  
   Descargar los datos de centros sanitarios y guardarlos como:  
   `raw_data/BancoDeDatos-centros-sanitarios.csv`  
   Fuente: https://terramapas.icv.gva.es/15_GERCA_wfs?request=GetFeature&service=WFS&version=2.0.0&typename=GERCA.Certificados&outputformat=csv

