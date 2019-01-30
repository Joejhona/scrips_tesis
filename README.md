# Scripts  NCL para Tesis de Geofisica

Para la Tesis de Maestria en Geofisica.
Conjunto de archivos ncl para elaborar difernetes mapas con el programa NCL.
Nacar Command Languages

## Pre requisitos 

* NCL V-6.4

## Acronimo

* ppd - lluvia diaria
* p99, p95, p90, p75 - percentil 99, 95, 90 y 75
* 

## Data Usada

* [piscoV2.0-piscoV2.1](ftp://ftp.senamhi.gob.pe/) - Peruvian Interpolated data of the SENAMHI’s Climatological and hydrological Observations
* [chirpsV2.0](http://chg.geog.ucsb.edu/data/chirps/#_Data) - Climate Hazards Group InfraRed Precipitation with Station data
* [estaciones senamhi](https://www.senamhi.gob.pe/?&p=estaciones) - Servicio Nacional de Meteorologia e Hidrologia
* [imergV5.0-opcion1](https://disc.gsfc.nasa.gov/) - Integrated Multi-satelliE Retrievals for GPM
* [imergV5.0-opcion2](https://disc.gsfc.nasa.gov/SSW/#keywords=) - Integrated Multi-satelliE Retrievals for GPM

    **NOTA** Para descargar datos imerg debes iniciar sesion [aqui](https://urs.earthdata.nasa.gov/home) 

## Detalle

A continuacion se detalla cada archivo, como funciona y cual es su producto o resultado.

## pisco-ppmax-81-16.ncl

Usa los datos de piscoV2.0 y V2.1 de 35 años (1981-2016) para determinar los valores minimos de ppd de p99, p95, p90 y p75, de un periodo determinado, de preferencia los meses de enero, febrero y marzo.

**MAPA** 8 mapas del Perú donde se aprecia los p99, p95, p90 y p75 del periodo seleccionado, la primera fila de mapas indica los percentiles considerando todos años y la segunda fila excluye los años 1983, 1998.

**RESULTADO** Dos archivos netcdf con las siguientes variables o matrices
1. **ppd_pi_t_per** con valores minimos de ppd de los p99, p95, p90 y p75 considerando todos años.
2. **ppd_pi_e_per** con valores minimos de ppd de los p99, p95, p90 y p75 excluye los años 1983, 1998.

![perc-piscov21-mar-81-16](https://user-images.githubusercontent.com/22982346/52011043-f67af300-24a4-11e9-8040-2dda58a7b1a4.png)

## chirps-ppmax-81-18.ncl

Similar a pisco-ppmax-81-16.ncl, usa la data chirps de 38 años (1981-2018) para el analisis, en la segunda fila de mapas excluye ademas el año 2017, las variables del archivo netcdf se denominan **ppd_ch_t_per** y **ppd_ch_e_per**

## pisco-ppmax-81-16-post.ncl

Usa los archivos netcdf creados por **pisco-ppmax-81-16.ncl** para dibujar los mapas de p99, p95, p90 y p75, de las mismas caracteristicas que **pisco-ppmax-81-16.ncl**

## percPISCO21.ncl

Genera una animación diaria de 8 mapas donde se puede observar en que parte del Perú se ha tenido valores mayores que el p99, p95, p90 y p75, usando la data de piscoV2.1 de 1981 al 2016 y la data diaria de pisco unstable, la primera fila es considerando todos años y la segunda fila excluye los años 1983, 1998.

**ANIMACION** 30 dias consecutivos de un mes seleccionado

## ppd-IMERG-vs-perc-pisco-E-17-18.ncl

Similar a percPISCO21.ncl, usa la data diaria de IMERG a cambio de la data diaria de pisco unstable.

## perc95PISCO21vsSENAMHI.ncl

Genera una animacion diaria de 3 mapas donde se puede observar de derecha a izquierda:
1. Mapa de p95 de data piscoV2.1 del mes seleccionado, excluyendo los años 1983 y 1998.
2. Mapa de ppd piscoV2.1 unstable donde se ha tenido valores mayores al p95 del mapa 1.
3. Mapa de ppd de las estaciones del SENAMHI donde se ha tenido valores mayores al p95 del mapa 1.

**ANIMACION** 30 dias consecutivos de un mes seleccionado

**RESULTADO** Archivo *.csv donde se indica las estaciones del senamhi que tienen valores mayores al p95.



## Autor

Joejhona