# Predicción de Daños Materiales en Accidentes Viales (México) 

Este projecto tiene como **objetivo** analizar y predecir los daños materiales provocados por accidentes viales en México, utilizando técnicas de **Análisis Exploratorio de Datos (EDA)** y **modelado predictivo con Machine Learning**. 

Los datos provienen de la base de datos [Acidentes de Tránsito por Mes](https://datos.gob.mx/dataset/accidentes_transito/resource/8a46ba6d-9d40-4029-8d7e-216feeff950e)  de la Secretaría de Infraestructura, Comunicaciones y Transportes (SICT). La estructura contiene información por mes y entidad federativa. 

## Estructura del Repositorio 
## Estructura del Dataframe 
El dataframe contiene la siguiente estructura
|**Variable**|**Descripción**|
|---|---|
|```entidad_federativa```|Entidad Federativa|
|```mes```|Mes del año|
|```accidentes```|Número de accidentes|
|```danios_materiales_millones```|Daños Materiales en millones de pesos debidos al accidente|
|```heridos```|Número de heridos en el accidente|
|```muertos``` |Número de fallecidos en el accidente|

## Análisis Exploratorio de Datos (EDA) 
Se realizó un EDA para comprender la estructura del dataset y detectar patrones releveantes antes del modelado. 
### Revisión inicial del dataset
- No se encontraron valores nulos
- Se revisaroon tipos de datos y rangos
- Se generó una variable adicional como el mes numérico

### Distribución de variables numéricas
- Accidentes, heridos, muertos y daños presentaron distribuciones sesgadas a la derecha.
- Se utilizará el uso de transformaciones logarítmicas para mitigar el sesgo.

### Análisis Temporal
- Se evaluaron tendencias mensuales y variaciones en accidentes y daños.

### Correlaciones 
- Accidentes y daños materiales mostraron la relación más fuerte.

## Preparación de Datos 
Transformaciones aplicadas:
- Aplicación de logaritmo para estabilizar distribuciones:
  - ```accidentes_log```
  - ```heridos_log```
  - ```muertos_log```
  - ```danios_log``` (variable objetivo)
- Creación de variables dummy para:
  - Entidad Federativa
  - Mes
- División de datos:
  - ```train_test_split``` con 20% para prueba.
