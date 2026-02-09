# Proyecto de prediccion de ventas /demanda de Walmart.
## Descripción del problema.
Se le proporcionan datos históricos de ventas de 45 tiendas Walmart ubicadas en diferentes regiones. Cada tienda cuenta con varios departamentos, y su tarea es predecir las ventas de cada departamento.

Además, Walmart organiza varias promociones de rebajas a lo largo del año. Estas rebajas preceden a festividades importantes, las cuatro más importantes de las cuales son el Super Bowl, el Día del Trabajo, el Día de Acción de Gracias y Navidad. Las semanas que incluyen estas festividades tienen una ponderación cinco veces mayor en la evaluación que las semanas sin festividades. Parte del desafío de esta competencia es modelar los efectos de las rebajas en estas semanas festivas ante la falta de datos históricos completos/ideales.

 ## Descripcion de las bases de datos

### stores.csv 
Contiene la información de 45 tiendas (anónimas) indicando el tipo y tamaño de la tienda

### train.csv
Estos son los datos históricos de entrenamiento, que abarcan del 05/02/2010 al 01/11/2012. En este archivo encontrará los siguientes campos:

-	Store: El numero de tiendas
-	Dept: El numero de departamento 
-	Date: La semana
-	Weekly_Sales: Ventas para el departamento dado en la tienda dada
-	IsHoliday: si la semana es una semana festiva especial


### test.csv  
Este archivo es idéntico a train.csv, excepto que hemos retenido las ventas semanales. Debe predecir las ventas para cada terna de tienda, departamento y fecha en este archivo.

### features.csv
Este archivo contiene datos adicionales sobre la actividad de la tienda, el departamento y la región para las fechas indicadas. Contiene los siguientes campos:

- Store - el numero de tienda
- Date - la semana
- Temperature - temperatura media en la región
- Fuel_Price - costo de combustible en la región
- MarkDown1-5 - Datos anónimos relacionados con las rebajas promocionales de Walmart. Los datos de rebajas solo están disponibles después de noviembre de 2011 y no están disponibles para todas las tiendas en todo momento. Cualquier valor faltante se marca con un NA.
- CPI - el índice de precios al consumidor
- Unemployment - la tasa de desempleo
- IsHoliday - si la semana es una semana festiva especial

Para mayor comodidad, los cuatro días festivos se incluyen en las siguientes semanas del conjunto de datos (no todos los días festivos están incluidos en los datos):

- Super Bowl: 12/02/2010, 11/02/2011, 10/02/2012, 8/02/2013
- Día del Trabajo: 10/09/2010, 9/09/2011, 7/09/2012, 6/09/2013
- Acción de Gracias: 26/11/2010, 25/11/2011, 23/11/2012, 29/11/2013
- Navidad: 31/12/2010, 30/12/2011, 28/12/2012, 27/12/2013

## Evaluación.
Tenemos que utilizar la fórmula de (WMAE).


$WMAE = \frac{1}{\sum w_{i}} \cdot \sum_{i=1}^{n} w_{i} \lvert y_{i} + \hat{y}_{i} \rvert$

donde n es el numero de filas, $\hat{y}$ son las ventas previstas, $y_{i}$ son las ventas actuales y $w_{i}$ son los pesos. 