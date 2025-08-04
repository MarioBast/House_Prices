# Proyección de ventas de viviendas por zona en Ames, Iowa utilizando Machine Learning
## Grupo 2
### UIDE
### Tratamiendo de datos
 
### Resumen
El presente trabajo analiza las características de las viviendas de la ciudad de Ames, Iowa, con el objetivo de identificar las razones por las que ciertas zonas presentan menos ventas y proyectar la cantidad de casas que se venderán en el año 2010 en cada vecindario. Se emplearon técnicas de análisis exploratorio, visualización de datos y Machine Learning (Random Forest) para realizar la proyección y detectar las zonas con mayor potencial inmobiliario. Los resultados muestran diferencias significativas entre las zonas comerciales y residenciales, aportando insumos útiles para el sector inmobiliario y la planificación urbana.
 
##### Palabras clave: ventas de viviendas, análisis urbano, machine learning, proyección, Ames
 
### Introducción
La predicción de ventas de viviendas y el análisis de factores que influyen en el éxito comercial de diferentes zonas urbanas es un tema de interés tanto para agentes inmobiliarios como para planificadores urbanos. En este estudio, se utiliza el reconocido dataset de Ames Housing para analizar las características principales que afectan las ventas y proyectar el comportamiento para el año 2010. Además, se emplea Machine Learning como herramienta predictiva y de apoyo al análisis.

### Metodología

#### Limpieza y Transformación de Datos

A continuación, se resumen los pasos principales realizados para limpiar y transformar los datos del proyecto:

#### 1. Carga y Exploración Inicial

- Se importó el archivo de datos `train.csv` utilizando la librería `pandas`.
- Se realizó una inspección básica del dataset con funciones como `.head()`, `.info()` y `.describe()` para entender la estructura de los datos y detectar valores faltantes o anómalos.

#### 2. Limpieza de Datos

- **Eliminación de columnas irrelevantes:**  
  Se eliminaron variables con alta proporción de valores nulos o que no aportaban valor analítico, tales como `PoolQC`, `MiscFeature`, `Alley`, entre otras.
- **Eliminación de outliers:**  
  Se identificaron y removieron registros con valores extremos en variables clave como `GrLivArea`, para evitar distorsión en el análisis y en los modelos predictivos.
- **Manejo de valores nulos:**  
  - Para variables numéricas, los valores faltantes se reemplazaron por la mediana o media de la columna.
  - Para variables categóricas, se usó la moda o un valor específico ("None") para los nulos.

#### 3. Transformación de Variables

- **Codificación de variables categóricas:**  
  - Se aplicó *Label Encoding* para convertir categorías en valores numéricos.
  - En algunos casos, se utilizó *One-Hot Encoding* para variables con pocas categorías distintas.
- **Creación de variables derivadas:**  
  - Se generaron nuevas variables combinando o transformando columnas existentes, como la antigüedad de la vivienda (`YearSold - YearBuilt`) o superficies totales.
- **Estandarización/Normalización:**  
  - Se normalizaron algunas variables numéricas para que fueran compatibles con los algoritmos de Machine Learning.

### 4. Selección de Variables

- Se seleccionaron únicamente las variables relevantes para el análisis, descartando aquellas que generaban ruido o duplicidad.

#### 5. División de Datos

- Se separaron los datos en variables predictoras (`X`) y variable objetivo (`y`).
- En etapas de modelado, se dividieron los datos en conjuntos de entrenamiento y prueba (*train/test split*).

#### 6. Procesos Adicionales

- Se realizó análisis exploratorio para identificar correlaciones y patrones relevantes.
- Se almacenaron datasets limpios y transformados en archivos auxiliares para su reutilización.
 
### 2. Análisis exploratorio y visualización
Se realizó una comparación entre la zona "C (all)" (comercial) y las zonas residenciales, evaluando métricas como:
 
- Cantidad de casas vendidas
 
- Superficie habitable promedio
 
- Precio promedio de venta
 
- Calidad y condición promedio
 
- Año promedio de construcción
 
Los resultados se presentaron en gráficos de barras horizontales, uno por cada característica, mostrando comparativamente la situación de cada zona.
 
#### 3. Modelado predictivo
Para la proyección de ventas en el año 2010, se empleó un modelo Random Forest Regressor, utilizando como variables predictoras:
 
- Promedios históricos de características físicas y económicas por zona
 
- Cantidad de ventas previas
 
- Codificación de la zona
 
Se entrenó el modelo con datos hasta 2009 y se proyectó el número de ventas por zona para el año 2010.
 
##### Resultados
El análisis comparativo mostró que la zona "C (all)", al ser comercial, tiene significativamente menos ventas, precios y calidad de viviendas, en contraste con las zonas residenciales que presentan mejores valores en todas las métricas analizadas.
  
El modelo de Machine Learning permitió proyectar la cantidad de casas vendidas en 2010 por zona, identificando los cinco vecindarios con mayores ventas proyectadas.

Se graficó la proyección de ventas por zona y se identificaron las zonas con mayor y menor potencial para el año proyectado.
 
##### Discusión
El análisis evidenció la importancia de la zonificación urbana y las características físicas de las viviendas en el volumen de ventas. Las zonas residenciales superan ampliamente en ventas a la zona comercial "C (all)", lo cual se atribuye tanto a la oferta disponible como a la demanda del mercado. La utilización de modelos predictivos de Machine Learning refuerza la capacidad de anticipar tendencias y apoyar la toma de decisiones.
 
##### Conclusiones
- La zona "C (all)" vende menos casas debido a su carácter comercial, baja oferta y menor atractivo residencial.
 
- Las zonas residenciales, en cambio, presentan mejores proyecciones de ventas y condiciones habitacionales.
 
- El Machine Learning es una herramienta eficaz para proyectar tendencias de ventas y aportar al análisis urbano.
 
##### Importancia del estudio
Este estudio es relevante porque integra el análisis exploratorio, la visualización y la modelización predictiva, brindando una herramienta práctica para la toma de decisiones en el sector inmobiliario y la planificación urbana. Además, demuestra la aplicabilidad del Machine Learning en contextos urbanos y su valor para la predicción de tendencias de mercado.
 
##### Referencias
 
Ames Housing Data. (2018). Kaggle. https://www.kaggle.com/c/house-prices-advanced-regression-techniques/data
 
Pedregosa, F., et al. (2011). Scikit-learn: Machine Learning in Python. Journal of Machine Learning Research, 12, 2825–2830.
