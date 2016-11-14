# Plantilla de Mapa

Plantilla de visualización para mapa de la república mexicana.<br>
Descripción de archivos principales:

- `mapa.html` <br>- Archivo html en el que se importan principalmente:
  * Librería de la visualización
  * Archivo `js` con diversas funcionalidades (`js/mapa.js`)
  * **Contendor para la gráfica**, que en este caso se debe definir en el html como: `<div id="mapMX" class="map"></div>`
  
- `partials/mxGeo.json`<br>- **GeoJson** con coordenadas para dibujar los polígonos de cada estado y en donde se definen los valores que mostrará la visualización en general y por cada estado.<br><br>

- `js/mapa.js`<br>- Javascript que contiene las funcionalidades **necesarias** para dibujar la visualización.
<br>

Para probar las visualizaciones en local, es necesario montar el proyecto en un servidor web local como Apache.

##Json base

El Json que consumirá la visualización debe estar en todo momento dentro del folder `partials` o en su defecto cambiar la ruta en la llamada Ajax dentro de `js/mapa.js`. Además debe tener asignado el nombre `mxGeo.json`<br>

La **estructura** debe ser igual a la del archivo `mxGeo.json`, si exisite alguna diferencia, por mínima que sea, la gráfica no se visualizará en el navegador.

Además los **nombres** o `keys` de los valores deben ser iguales a los dej Json de ejemplo para que estos se puedan mostrar en la visualización.

**Estructura**

```
{
  "type": "FeatureCollection",
  "etiqueta_info": "Etiqueta ejemplo:",
  "etiqueta_pop": "Porcentaje ejemplo:",
  "ejex": "Año",
  "ejey": "Valor",
  "features": [
    {
      "type": "Feature",
      "geometry": {
      ...
     },
     "properties": {
        "valor_info": "47",
        "porcentaje_pop": 32,
        "estado": "Sinaloa",
        "grafica": [
          {
             "tiempo": "2008",
             "valor": 10
           },
           {
            "tiempo": "2009",
            "valor": 5
          },
          {
            "tiempo": "2010",
            "valor": 2
          }
        ]
      }
    }
  ]
}
```

**Valores editables**

- "etiqueta_info" //Leyenda del Info Box
- "etiqueta_pop" //Leyenda del Tooltip
- "ejex" //Leyenda del Eje X en la gráfica
- "ejey" //Leyenda del Eje Y en la gráfica
- "valor_info" //Valor mostrado en el info Box
- "porcentaje_pop" //Porcentaje mostrado en el Tooltip
- "grafica" //Cada objeto dentro de este array es un punto en la gráfica que se dibuja dentro del Info Box.
 
**Importante: No cambiar los demás nombres o valores del Geojson, ya que con cualquier error, el mapa no se visualizará en el navegador**
