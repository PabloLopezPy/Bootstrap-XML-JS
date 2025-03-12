# Visor de Feeds ATOM RSS

Una aplicación web para cargar, procesar y mostrar feeds en formato ATOM RSS utilizando Bootstrap 5, jQuery y JavaScript moderno.

## Características

- **Carga de feeds ATOM**: Permite introducir URLs de feeds ATOM RSS para visualizar su contenido.
- **Validación XML**: Verifica que el feed cumpla con el estándar XML ATOM.
- **Visualización en tarjetas**: Muestra las noticias en un formato de cards Bootstrap responsive.
- **Marcar favoritos**: Permite marcar noticias como favoritas y filtrar para ver solo las favoritas.
- **Búsqueda y filtrado**: Incluye búsqueda de texto y filtrado por categorías.
- **Paginación**: Muestra 10 noticias por página con navegación completa.
- **Vistas alternativas**: Permite cambiar entre vista de tarjetas y lista.
- **Gestión de fuentes**: Permite guardar y gestionar múltiples fuentes de feeds.
- **Almacenamiento local**: Guarda favoritos y fuentes en localStorage del navegador.

## Instalación y configuración

### Requisitos previos

No se requiere ninguna instalación especial, ya que la aplicación es puramente frontend y funciona en cualquier navegador moderno:

- Navegador web actualizado (Chrome, Firefox, Edge, Safari)
- Conexión a Internet para cargar feeds y librerías externas

### Instalación rápida

1. Descarga todos los archivos del proyecto a una carpeta en tu computadora.
2. Abre el archivo `index.html` directamente en tu navegador.

### Instalación con servidor web local (recomendado)

Para evitar posibles restricciones CORS al cargar feeds, es recomendable ejecutar la aplicación desde un servidor web:

#### Usando Python (opción simple)

```bash
# Python 3.x
python -m http.server 8000

# Python 2.x
python -m SimpleHTTPServer 8000
```

#### Usando Node.js y http-server

```bash
# Instalar http-server globalmente
npm install -g http-server

# Ejecutar en la carpeta del proyecto
http-server -p 8000
```

Luego abre `http://localhost:8000` en tu navegador.

## Estructura del proyecto

```
/
│   index.html            # Página principal
│   styles.css            # Estilos CSS 
│   rss-viewer.js         # Lógica principal de la aplicación
│   atom-validator.js     # Funciones de validación XML ATOM
│   README.md             # Este archivo
```

## Cómo usar

1. Abre `index.html` en tu navegador.
2. Introduce la URL de un feed ATOM en el campo correspondiente y haz clic en "Cargar Feed".
3. Explora las noticias, marca favoritos, utiliza la búsqueda y los filtros.
4. Las fuentes y favoritos se guardarán automáticamente.

## Ejemplos de feeds ATOM

- Ministerio de Economía: `https://portal.mineco.gob.es/es-es/Paginas/RSSFeed.aspx?source=http://www.mineco.gob.es/portal/site/mineco/menuitem.ac30f9268750bd56a0b0240e026041a0/?vgnextoid=3a420f451958b310VgnVCM1000001d04140aRCRD`
- Parlamento Europeo: `https://www.europarl.europa.eu/rss/doc/press-news/es.xml`
- El Mundo: `http://rss.elmundo.es/rss/descarga_portada_rss.html`

## Tecnologías utilizadas

- **Bootstrap 5**: Para el diseño responsive y componentes de UI.
- **jQuery**: Para manipulación del DOM y peticiones AJAX.
- **JavaScript ES6+**: Para la lógica de la aplicación.
- **HTML5/CSS3**: Para la estructura y estilos.
- **LocalStorage API**: Para almacenamiento en el navegador.

## Funcionalidades técnicas

### Validación XML

El sistema valida que el feed ATOM cumpla con las especificaciones básicas:
- Verifica que exista un elemento `feed` raíz.
- Comprueba que el namespace de ATOM sea correcto.
- Verifica elementos obligatorios como `id`, `title` y `updated`.
- Comprueba que cada entrada tenga los elementos requeridos.

### Procesamiento de feeds

La aplicación extrae la siguiente información de cada entrada:
- Título
- Autor
- Fecha de actualización
- Resumen o contenido
- Enlace
- Categorías
- Imagen (si está disponible)

### Gestión de estado

La aplicación mantiene un estado global que incluye:
- Feeds cargados
- Entradas totales
- Entradas filtradas actuales
- Favoritos
- Página actual
- Configuración de visualización
- Fuentes guardadas

## Solución de problemas comunes

### Error de CORS al cargar feeds

Si recibes errores relacionados con CORS al intentar cargar feeds:

1. **Usa un servidor proxy CORS**: Configura la aplicación para usar un proxy CORS.
2. **Ejecuta en un servidor local**: Sigue las instrucciones de instalación con servidor web local.
3. **Utiliza extensiones de navegador**: Como "CORS Unblock" para Chrome.

### Feeds que no cargan correctamente

Si un feed no se carga o muestra errores:

1. Verifica que la URL sea correcta y esté accesible.
2. Asegúrate de que el feed sea realmente en formato ATOM (no RSS).
3. Intenta abrir la URL directamente en el navegador para ver si devuelve XML válido.

### Problemas de almacenamiento local

Si las fuentes o favoritos no se guardan correctamente:

1. Verifica que tu navegador tenga habilitado el almacenamiento local.
2. Intenta limpiar la caché del navegador y recargar la página.
3. Si usas un modo de navegación privada, ten en cuenta que localStorage no persistirá.

## Posibles mejoras

- Añadir soporte para feeds RSS además de ATOM.
- Implementar validación XSD completa usando una biblioteca especializada.
- Añadir exportación/importación de configuración.
- Implementar modo oscuro.
- Añadir soporte para PWA (Progressive Web App).
- Integrar un backend para guardar los datos en servidor.

## Recursos

### Bootstrap
- [Documentación oficial](https://getbootstrap.com/docs/)
- [Bootstrap Studio](https://bootstrapstudio.io/)
- [Build Bootstrap](https://bootstrap.build/app)

### XML/XSD en JavaScript
- [libxmljs](https://github.com/libxmljs/libxmljs)
- [xsdlib](https://github.com/sublimedatasys/xsdlib)

### Fuentes ATOM
- [RSS El Mundo](http://rss.elmundo.es/rss/)
- [RSS Ministerio de Economía](https://portal.mineco.gob.es/es-es/ministerio/Paginas/Info_RSS.aspx)
