# Plantilla de Mapa (Versión 2)

Plantilla de visualización para mapa de la república mexicana.<br>
Esta versión utiliza un json por cada estado para mostrar los datos y valores, el GeoJson queda solo para los datos geoespaciales y valores generales de la visualización como las etiquetas.<br>
Descripción de archivos principales:

- `mapa.html` <br>- Archivo html en el que se importan principalmente:
  * Librería de la visualización
  * Archivo `js` con diversas funcionalidades (`js/mapa.js`)
  * **Contendor para la gráfica**, que en este caso se debe definir en el html como: `<div id="mapMX" class="map"></div>`

- `partials/mxGeo.json`<br>- **GeoJson** con coordenadas para dibujar los polígonos de cada estado. En esta versión, este archivo ya no contiene datos ni valores por estados.<br><br>

- Se agregaron los archivos json **para cada estado** por separado en la carpeta `partials/`

- `js/mapa.js`<br>- Javascript que contiene las funcionalidades **necesarias** para dibujar la visualización.
<br>

Para probar las visualizaciones en local, es necesario montar el proyecto en un servidor web local como Apache.

##GeoJson

El archivo GeoJson que utiliza la visualización para dibujar los poligonos debe estar en todo momento dentro del folder `partials` o en su defecto cambiar la ruta en la llamada Ajax dentro de `js/mapa.js`.  y debe tener asignado el nombre `mxGeo.json`<br>

**Valores editables en GeoJson (Se aplican en general a todos los estados)**

- "etiqueta_info" //Leyenda del Info Box
- "etiqueta_pop" //Leyenda del Tooltip
- "ejex" //Leyenda del Eje X en la gráfica
- "ejey" //Leyenda del Eje Y en la gráfica

##Json por estado

En la ruta `partials/` se encuentran los archivos Json para cada estado y son los que se deben modificar con los datos que se deseen mostrar en cada región. Se recomienda que estos archivos se llamen tal y como vienen por default en el repositorio, ya que se hace un match con `partials/mxGeo.json`.

La estructura es igual para todos los archivos json de cada estado. Además los **nombres** o `keys` de los valores deben ser iguales a los del Json de ejemplo para que estos se puedan mostrar en la visualización.

**Estructura**

```
{
  "valor_info": "33.25",
  "porcentaje_pop": 32,
  "estado": "Durango",
  "grafica": [
    {
      "tiempo": "2008",
      "valor": 250
    },
    {
      "tiempo": "2009",
      "valor": 262
    },
    {
      "tiempo": "2010",
      "valor": 274
    },
    {
      "tiempo": "2011",
      "valor": 280
    },
    {
      "tiempo": "2012",
      "valor": 291
    },
    {
      "tiempo": "2013",
      "valor": 301
    },
    {
      "tiempo": "2014",
      "valor": 311
    }
  ]
}
```

**Valores editables (aplican individualmente por estado)**

- "valor_info" //Valor mostrado en el info Box
- "porcentaje_pop" //Porcentaje mostrado en el Tooltip
- "grafica" //Cada objeto dentro de este array es un punto en la gráfica que se dibuja dentro del Info Box.

