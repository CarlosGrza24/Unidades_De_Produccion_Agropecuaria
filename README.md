# Modelado de unidades de producción agropecuarias activas a partir de sistemas de riego

Este proyecto analiza la relación entre los distintos **sistemas de riego** y el **total de unidades de producción agropecuaria activas (UP)** en México. El 
objetivo es estimar el comportamiento de estas unidades y determinar qué factores tienen mayor influencia, comparando un modelo lineal y uno no lineal (KNN). La 
hipótesis es que la **tecnificación del riego** (aspersión, pivote central, aspersores, etc.) se asocia de manera positiva con un mayor número de UP activas.

Los datos provienen del **Censo Agropecuario 2022 (INEGI)**, disponibles públicamente en la plataforma oficial de descargas:
- [INEGI – Censo Agropecuario 2022, archivo.csv](https://www.inegi.org.mx/app/descarga/ficha.html?tit=1795268&ag=0&f=csv)

Archivo utilizado: [CA2022_Cultivos_Superficie_Produccion.csv](CA2022_Cultivos_Superficie_Produccion.csv)  

## Datos utilizados
Del archivo [DiccionarioDeDatos.csv](DiccionarioDeDatos.csv), las variables incluidas en el dataset son:

- NOM_MUN → Nombre del municipio  
- ENTIDAD → Nombre de la entidad federativa  
- NOMBRE → Nombre de la UP  
- Total UP agropecuaria activas → Total de unidades de producción activas  
- UP Agricolas → Total de UP agrícolas  
- UP Argri Riego (R) → UP agrícolas con riego  
- UP Riego Gravedad (RG) → UP con riego por gravedad  
- UP R Por Microaspersión → UP con riego por microaspersión  
- UP R Por Aspersión → UP con riego por aspersión general  
- UP R Por Aspersión Pivote Central → UP con riego por pivote central  
- UP R Por Aspersión Avance Frontal → UP con riego por avance frontal  
- UP R Por Aspersión Cañón → UP con riego por aspersión de cañón  
- UP R Por Aspersores → UP con riego por aspersores  
- UP R Sistema De Goteo → UP con riego por goteo  

## Metodología

1. **Exploración inicial**
   - Revisión de dimensiones, tipos de datos y primeras observaciones.  
   - Visualización de la variable objetivo para identificar distribución y outliers.  

2. **Limpieza y preprocesamiento**
   - Eliminación de identificadores irrelevantes.  
   - Control de outliers con método de *Tukey*.  
   - Revisión de colinealidad y exclusión de variables redundantes.  

3. **Selección de características**
   - Métodos forward y backward aplicados de forma híbrida.  
   - Selección final: 4 predictores clave.  

4. **Modelado**
   - División *80/20* en train/test.  
   - *Regresión lineal* con statsmodels
   - Método No lineal utilizando *KNN*

5. **Evaluación**
   - Métricas en test: *R²* y *RMSE*.  

6. **Inferencia**  
   - Revisar los coeficientes del modelo lineal y analizar si las variables seleccionadas tienen un efecto positivo o negativo sobre la respuesta.  
   - Verificar la significancia estadística de cada predictor usando p-values e intervalos de confianza.  
   - Estimar un valor promedio de la variable dependiente y mostrar márgenes de error para interpretar la precisión del modelo.  
   - Presentar un intervalo de predicción que refleje la variabilidad esperada en observaciones individuales.

## Archivos del proyecto
- [Reporte en ipynb](P1_648241.ipynb)
- [Reporte en html](P1_648241.html)  
- [CA2022_Cultivos_Superficie_Produccion.csv](CA2022_Cultivos_Superficie_Produccion.csv)  
- [DiccionarioDeDatos.csv](DiccionarioDeDatos.csv)
