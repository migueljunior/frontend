# Frontend (HTML - CSS)
## HTML
Este repositorio es para mejorar los skills en frontend, por lo que sera una documentacion de distintos temas de HTML y CSS.

HTML significa Hypertext Markup Language, Lenguaje marcado de hipertexto. La anatomía de una página web es la siguiente:

- **Container:** contenedor principal
    - **Header:** cabecera de la página. Aquí usualmente encuentras el logo y el menú de navegación del sitio.
        - Logo
        - Navigation
    - **Main Content:** estructura principal. Por ejemplo, el feed o lista de publicaciones de una red social.
    - **Sidebar:** contenido secundario de una página, que usualmente se encuentra a los lados del contenido principal (o main).
    - **Footer:** pie de página. Esto se encuentra al fondo del sitio web, salvo en casos de sitios web donde el scroll (o navegación hacia abajo) es infinito, por ende, no tendría sentido ponerlo al fondo.

index.html es la pagina inicial que el servidor busca para abrirlo incialmente, de no existir este archivo hay que decir explicitamente al servidor que archivo abrira.

En la etiqueta head van ligados los recursos que se utilizaran en la web pero el usuario no tiene acceso a esta, el usuario solo vera el contenido de la etiqueta body.

### Anatomia de una etiqueta
Etiqueta de apertura y etiqueta de cierre. El atributo es lo que va en la etiqueta de apertura. Lo que se encuentra en el medio de las etiquetas es el contenido y el conjunto del todo es el elemento.

### Tipos de imagenes
Existen dos tipos de imagenes, sin perdida (Lossless) o con perdida (Lossy), y esto depende de como el formato maneja las imagenes.

- **Lossless:** Sin perdida, capturan todos los datos de su archivo original. No se pierde nada del archivo original, foto u obra de arte. El archivo aun puede estar comprimido, pero todos los formatos sin perdida podran reconstruir su imagen a su estado original.
- **Lossy:** Con perdida, se aproxima a su imagen original, puede reducir la cantidad de colores en su imagen, por lo general son mucho mas pequeñas son ideales para cargar de manera rapida la web.

GIF (Graphics Interchange Format) - Lossless.
PNG (Portable Network Graphics) - Lossless.
JPG/JPEG (Photographic Experts Group) - Lossy.
SVG/Vector (Scalable Vector Graphics) - Lossless.

Peso promedio de imagenes 70 Kb, para optimizar las imagenes se puede utilizar Tiny PNG o Verexif

### Etiqueta img
Es necesario descargar imagenes para mostrarlos con la etiqueta img se puede utilizar el siguiente codigo:
```
<img src="ruta de la imagen" alt="descripcion de la imagen">
```
En el atributo src se puede utilizar un file o una url de una imagen.
Atributo alt muestra una descripcion al navegador si es que la imagen no carga por alguna razon y tambien ayuda en la accesibilidad.

### Etiqueta figure
Contiene a la etiqueta img, puede reemplazar a la etiqueta div
```
<figure>
    <img src="ruta de la imagen" alt="descripcion de la imagen">
    <figcaption>Descripcion de la imagen</figcaption>
</figure>
```
Esta descrippcion de píe que se muestra al cliente para mostrar informacion de la imagen al usuario.

### Etiqueta Video
Esta etiqueta se lo utiliza de la siguiente forma:
```
<video src="ruta del video" controls preload="auto"></video>
```
Atributos importantes:
- **controls:** Este atributo no tiene valor
- **preload:** Ayuda a que el video se empiece a renderizar cuando se esta cargando la pagina, no significa que se reproducira solo (esta es una mala practica)
Una extension de **source** es el siguiente:
```
<video src="ruta del video#t=10,60" controls preload="auto"></video>
```
El cual indica que iniciara en el segundo 10 y se detendra en el segundo 60.
Para que los navegadores entiendan diferentes formatos se realiza de la sigueinte manera:
```
<video controls preload="auto">
    <source src="ruta del video.mp4">
    <source src="ruta del video.mkv">
</video>
```
El navegador seleccionara el formato que entienda, lo que si respetara el primero si reconoce todos los formatos.

### Formularios
Estas etiquetas nos ayuda a solicitar informacion al usuario, se tienen que realizar de la mejor forma para que no sea tedioso para el usuario.
Es necesario que se utilice de manera semantica por lo que es necesario utilizar la etiqueta **form**. Ver la carpeta form para ver las buenas practicas.

Para ver los distintos tipos de inputs en HTML5 se puede consultar el siguiente enlace [Guia de inputs](https://developer.mozilla.org/es/docs/Web/HTML/Element/input "Guide of inputs").

## Autocomplete y require
Es necesario que los formularios sean amigables con los usuarios, tanto para autocompletar informacion recurrente que utiliza el usuario asi como indicarle que campos son obligatorios necesarios, esto ultimo se puede hacer con JS pero es bueno empezar a utilizar una primara capa de validacion de la informacion. La manera de realizar un autocompletado es con el siguiente atributo ```autocomplete="<value>"``` Done value son distintos tipos de valores que podemos ver en el siguiente [link](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/autocomplete "Autocomplete of inputs").

Y para que un campo sea mandatorio simplemente es utilizando el atributo ```required```

Para poder dar al usuario distintas selecciones se puede utilizar la etiqueta ``select``

## Diferencia entre input y button
La personalizacion de los botones, input se puede utilizar de forma directa en los formularios, la etiqueta button se puede utilizar para cualquier otro tipo de button que se necesite en el proyecto.

## CSS
Es un documento que aplica todos los estilos en forma de cascada, es el estandar para poder estilizar el proyecto.
Hay 3 formas para utilizar CSS:
- Importando un hajo de estilo con la etiqueta ``<link rel="stylesheet" href="./style.css">`` en el head
- Utilizando la etiqueta ``<style></style>`` en le head
- Implementando directamente en las etiquetas de archivo HTML ``<p style="color: red;">Soy un texto</p>``

Para especificar como aplicar los estilos se pueden realizar de la siguiente manera:
- Por la etiqueta
- Por la clase, agregando ``class='nombre de la clase'`` a la etiqueta y en la hoja de estilo ``.<nombre de la clase>``
- Por el ID, agregando ``id='nombre del ID'``a la etiqueta y en la hoja de estilo ``#<nombre del ID>``

### Pseudo clases y Pseudo elementos
