# Molinetes
![alt text](http://k37.kn3.net/taringa/1/6/3/7/6/7/84/anton_newcombe/8CE.jpg?3329)

### Analisis temporal de **Molinetes - Subte CABA** periodo **2015-2017**.

Analizar el comportamiento temporal de la cantidad de personas que utilizan el servicio de transporte Subterraneo en CABA.
Utilizamos modelos temporales analizando sus tres componentes
1) tendencia 
2) su ciclo estacional
3) su propia regularidad o irregularidad pura

```r

library(forecast)
library(zoo)
library(timeDate)
```
Los datos los obtuve a partir de la iniciativa del GCBA de "Apertura de Datos" https://data.buenosaires.gob.ar/datasets?categories.slug=movilidad-y-transporte.


```r
# Necesitamos convertir nuestro dataset en un objeto que R
# reconozca como Serie Temporal.  Cubriremos dos formatos de varios formatos,

fechas <- with(subte, ISOdate(año, mes, dia))
```

```r
subtes <- zoo(x = subte$u, order.by = fechas)
...
