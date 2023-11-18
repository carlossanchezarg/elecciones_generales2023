### Analisis de los resultados de las elecciones generales 2023

* *Fuente de datos: https://www.argentina.gob.ar/dine/resultados-electorales/elecciones-2023*
#### Los resultados están un archivo .csv, cuyas columnas siguen la siguiente especificación:
https://www.argentina.gob.ar/sites/default/files/preservacionresultadoselectorales_1.0.7.pdf
| Nombre               | Tipo              | Descripción                                                                                   | Valores Esperados                                      |
|----------------------|-------------------|-----------------------------------------------------------------------------------------------|--------------------------------------------------------|
| año                  | Entero            | Año calendario de la elección                                                                |                                                        |
| eleccion_tipo        | Cadena de caracteres | Tipo de elección                                                                           | PASO, GENERAL, SEGUNDA VUELTA                           |
| eleccion_id          | Entero            | Identificador numérico del tipo de elección                                                   |                                                        |
| recuento_tipo        | Cadena de caracteres | Tipo de recuento origen de los datos                                                       | PROVISORIO, DEFINITIVO                                   |
| recuento_id          | Entero            | Identificador numérico del tipo de recuento                                                   |                                                        |
| padron_tipo          | Cadena de caracteres | Tipo de padrón del cual provienen los datos                                                | NORMAL, COMANDO, PRIVADOS DE LA LIBERTAD, RESIDENTES EN EL EXTERIOR |
| distrito_id          | Entero            | Identificador numérico del distrito origen de los datos                                       |                                                        |
| distrito_nombre      | Cadena de caracteres | Nombre del distrito origen de los datos                                                      | Ver valores descriptos en la sección 4.1 - Identificadores de distritos |
| seccionprovincial_id | Entero            | Identificador numérico de la sección provincial origen de los datos                           |                                                        |
| seccionprovincial_nombre | Cadena de caracteres | Nombre de la sección provincial origen de los datos                                        | Puede ser nulo si el distrito no tiene secciones provinciales |
| seccion_id           | Entero            | Identificador numérico de la sección origen de los datos                                       |                                                        |
| seccion_nombre       | Cadena de caracteres | Nombre de la sección origen de los datos                                                      |                                                        |
| circuito_id          | Cadena de caracteres | Identificador numérico o alfanumérico del circuito origen de los datos                         |                                                        |
| circuito_nombre      | Cadena de caracteres | Nombre del circuito origen de los datos                                                       |                                                        |
| mesa_id              | Entero            | Identificador de la mesa origen de los datos                                                |                                                        |
| mesa_tipo            | Cadena de caracteres | Tipo de mesa origen de los datos                                                             | NATIVOS, EXTRANJEROS                                    |
| mesa_electores       | Entero            | Cantidad de electores de la mesa origen de los datos                                           |                                                        |
| cargo_id             | Entero            | Identificador del cargo para el cual se han contado los votos                                  |                                                        |
| cargo_nombre         | Cadena de caracteres | Nombre del cargo para el cual se han contado los votos                                        | Ver valores descriptos en la sección 4.2 - Identificadores de cargos electorales |
| agrupacion_id        | Cadena de caracteres | Indicador de la agrupación política. Puede ser nulo en el caso de votos no positivos         |                                                        |
| agrupacion_nombre    | Cadena de caracteres | Nombre de la agrupación política a la cual se han consignado los votos. Puede ser nulo en el caso de votos no positivos |
| lista_numero         | Cadena de Caracteres | Número de la lista de la agrupación política a la cual se han consignado los votos. Puede ser nulo en el caso de votos no positivos y en caso de elecciones generales |
| lista_nombre         | Cadena de caracteres | Nombre de la lista a la cual se han consignado los votos. Puede ser nulo en el caso de votos no positivos y en caso de elecciones generales |
| votos_tipo           | Cadena de caracteres | Tipo de votos que se han contabilizado                                                      | POSITIVO, EN BLANCO, IMPUGNADO, RECURRIDO, NULO, COMANDO |
| votos_cantidad       | Entero            | Cantidad de votos contabilizados                                                              |                                                        |
| estado_final         | Cadena de caracteres | Indica si el telegrama ha sido totalizado en el recuento provisional. Puede ser nulo para los recuentos definitivos | ESCRUTADO, NO ESCRUTADO                                  |

#### Para analizar:  
- [ ] Calcular las siguientes métricas para detectar fraude o irregularidades en las mesas escrutadas:   
     - [ ] Ceros: Mesas con cero votos o con candidatos con cero votos.   
     - [ ] Media, Mediana, cuartiles.  
     - [ ] Tabla para métricas:   

| Cargo |Agrup. |   Métrica   |Valor (%) |  
|:-----:|:----:|:-----------:|:--------:|     
| Pres  | Ag   | Mesas nulas |   9999   |  

- [ ] Errores: todo lo geográfico + tipo de error + N.º de casos + %  

Referencias:
- [1] GeoJSON con limites interdepartamentales fueron obtenidos del IGN https://www.ign.gob.ar/NuestrasActividades/InformacionGeoespacial/CapasSIG
