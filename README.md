# MapaMex

Plantilla de visualización tipo mapa plot.<br>
Descripción de archivos principales:

- `mapa.html` <br>- Archivo html en el que se importan principalmente:
  * Librería de la visualización
  * Archivo `js` con diversas funcionalidades (`js/mapa.js`)
  * **Contendor para la gráfica**, que en este caso se debe definir en el html como: `<div id="mapMX" class="map"></div>`

  <br>  
  
- `partials/mxGeo.json`<br>- **Json base** para definir los valores que mostrará la visualización, se debe respetar la **estructura** y los **nombres** o `keys` de los valores.<br><br>

- `js/mapa.js`<br>- Javascript que contiene las funcionalidades **necesarias** para dibujar la visualización.
<br><br>

Para probar las visualizaciones en local, es necesario montar el proyecto en un servidor web local como Apache.