# Checklist Front-End 
[![CC0](https://img.shields.io/badge/license-CC0-green.svg)](https://creativecommons.org/publicdomain/zero/1.0/)
[![Contributors](https://img.shields.io/github/contributors/thedaviddias/Front-End-Checklist.svg)](https://github.com/thedaviddias/Front-End-Checklist/graphs/contributors)

El **Checklist Front-End** es una lista exhaustiva de todos los elementos que debe considerar / probar antes de lanzar un sitio / página HTML a producción.

Se basa en los años de experiencia de los desarrolladores de Front-End, y añade algunas otras cosas de checklists de código abierto.

## Contenido
1. **[Como usar](#how-to-use)**
2. **[Cabecera (Head)](#head)**
3. **[HTML](#html)**
4. **[Webfonts](#webfonts)**
5. **[CSS](#css)**
6. **[Imágenes](#images)**
7. **[JavaScript](#javascript)**
8. **[Rendimiento](#performance)**
9. **[Accesibilidad](#accessibility)**
10. **[SEO](#seo)**

## ¿Como usar?

Todos los elementos de la **Checklist Front-End** son necesarios para la mayoría de los proyectos, pero algunos elementos pueden omitirse o no ser esenciales (en el caso de una aplicación web de administración, es posible que no necesite un feed RSS, por ejemplo). Elegimos utilizar 3 niveles de flexibilidad:

* ![Low](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-low.png) quiere decir que es **recomendado** pero puede ser emitido en caso particulares.
* ![Medium](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-medium.png) quiere decir que es **altamente recomendado** y puede ser omitido en casos muy particulares. Algunos elementos, si son omitidos por algún motivo, pueden tener repercusiones negativas en el rendimiento o en el SEO.
* ![High](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) quiere decir que **no puede ser omitido** por ningún motivo. Podría causar un mal funcionamiento de la página o tener problemas de rendimiento o SEO. Las prioridades de pruebas deben ponerse acá.

Algunos recursos poseen un ícono para ayudar a comprender qué tipo de contenido / ayuda puede encontrar en el checklist

* 📖: documentación o artículo
* 🛠: herramienta de pruebas
* 📹: contenido de audio o video

---
## Cabecera (Head)

> **Notas:** Puede revisar una [completa lista](https://github.com/joshbuchea/HEAD) de lo que podemos encontrar en el `<head>` de un documento HTML.

### Meta tag

* [ ] **Doctype:** ![High](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) El Doctype es HTML5 y está arriba en todos los documentos HTML.
 
```html
<!-- Doctype HTML5 -->
<!DOCTYPE html>
```

> 📖 [Determinación de la codificación de caracteres - HTML5 W3C](https://www.w3.org/TR/html5/syntax.html#determining-the-character-encoding)

*los siguientes 3 meta tags (Charset, X-UA Compatible and Viewport) necesitan ir primero en la lista de cabeceras.*

* [ ] **Charset:** ![High](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) El juego de caracteres declarado (UTF-8) se declara correctamente.

```html
<!-- Set character encoding for the document -->
<meta charset="utf-8">
```

* [ ] **X-UA-Compatible:** ![Medium](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-medium.png) El meta tag X-UA-Compatible está presente.
 
```html
<!-- Instruct Internet Explorer to use its latest rendering engine -->
<meta http-equiv="x-ua-compatible" content="ie=edge">
```

> 📖 [Especificar modos legacy (Internet Explorer)](https://msdn.microsoft.com/en-us/library/jj676915(v=vs.85).aspx)

* [ ] **Viewport:** ![High](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) El viewport se declara correctamente.

```html
<!-- Viewport for responsive web design -->
<meta name="viewport" content="width=device-width, initial-scale=1">
```

* [ ] **Title:** ![High](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) Un título es usado para todas las páginas (SEO: No más de 65 caracteres, incluyendo el nombre del sitio)

```html
<!-- Document Title -->
<title>Titulo de menos de 64 caracteres</title>
```

> 📖 [Título - HTML | MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/title)

* [ ] **Descripción:** ![High](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) Se proporciona una meta descripción, única y con 150 caracteres como máximo.

```html
<!-- Meta Description -->
<meta name="description" content="Descripción de menos de 150 caracteres">
```

* [ ] **Favicons:** ![Medium](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-medium.png) Cada favicon se ha creado y se muestra correctamente. Si solo existe un ``favicon.ico``, colóquelo en la raíz del sitio. Normalmente no se necesita ningún marcado. Sin embargo, es buena práctica vincularlo usando el siguiente ejemplo. Actualmente **el formato PNG es el recomendado** sobre el formato ``.ico`` (dimensiones: 32x32px)
 
```html
<!-- Standard favicon -->
<link rel="icon" type="image/x-icon" href="https://example.com/favicon.ico" />
<!-- Recommended favicon format -->
<link rel="icon" type="image/png" href="https://example.com/favicon.png" />
``` 

> * 🛠 [Generador Favicon](https://www.favicon-generator.org/)
> * 🛠 [RealFaviconGenerator](https://realfavicongenerator.net/)
> * 📖 [Favicon Cheat Sheet](https://github.com/audreyr/favicon-cheat-sheet)
> * 📖 [Favicons, Touch Icons, Tile Icons, etc. Which Do You Need? - CSS Tricks](https://css-tricks.com/favicon-quiz/)
> * 📖 [Favicons PNG - caniuse](http://caniuse.com/#feat=link-icon-png)

* [ ] **Icono Apple Touch:** ![Low](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-low.png) El favicon Apple touch apple-mobile-web-app-capable está presente. *(Cree su archivo ícono Apple con dimensiones de al menos 200x200 pixeles para admitir todas las dimensiones que pueda necesitar)*

```html
<!-- Apple Touch Icon -->
<link rel="apple-touch-icon" href="/custom-icon.png">
```
> * 📖 [Configurando Aplicaciones Web](https://developer.apple.com/library/content/documentation/AppleApplications/Reference/SafariWebContent/ConfiguringWebApplications/ConfiguringWebApplications.html)

* [ ] **Canonical:** ![Medium](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-medium.png) Use ``rel="canonical"`` para evitar contenido duplicado.

```html
<!-- Helps prevent duplicate content issues -->
<link rel="canonical" href="http://example.com/2017/09/a-new-article-to-red.html">
```

### HTML tags
* [ ] **Idioma:** ![High](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) La etiqueta de idioma de su sitio web se especifica y está relacionada con el idioma de la página actual.

```html
<html lang="en">
```

* [ ] **Dir tag:** ![Medium](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-medium.png) La dirección o sentido en que se debe leer el contenido se especifica en una etiqueta del cuerpo.

```html
<html dir="rtl">
```
```p
<p dir="rtl">Lea este texto de derecha-a-izquierda! (rtl=right-to-left)</p>
```

> 📖 [dir - HTML | MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/dir)

* [ ] **hreflang tag y lenguaje alternativo:** ![Low](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-low.png) La etiqueta de idioma de su sitio web se especifica y está relacionada con el idioma de la página actual.

```html
<link rel="alternate" href="https://es.example.com/" hreflang="es">
```

* [ ] **Comentarios condicionales:** ![Low](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-low.png) Los comentarios condicionales están presentes para IE si es necesario.

> 📖 [Acerca de los comentarios condicionales (Internet Explorer) - MSDN - Microsoft](https://msdn.microsoft.com/en-us/library/ms537512(v=vs.85).aspx)

* [ ] **Feed RSS:** ![Low](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-low.png) Si el proyecto es un blog o tiene artículos, se proporcionó un enlace RSS.

* [ ] **CSS Critical:** ![Medium](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-medium.png) El CSS crítico ("above the fold") recoge todos los CSS fundamentales utilizados para representar la capa visible de la página. Está incrustado antes de su llamada CSS principal, entre etiqueta ``<style></style>``, en una sola línea y minificada.

> 🛠 [Critical por Addy Osmany on Github](https://github.com/addyosmani/critical)

* [ ] **Orden CSS:** ![High](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) Todos los archivos CSS se cargan antes que cualquier archivo JavaScript en el bloque ``<head></head>``. (Excepto el caso, donde se cargan los archivos JS de manera asíncrona en la parte superior de su página).

### Social meta 

***Open Graph de Facebook*** y ***Cards de Twitter *** son altamente recomendados para cualquier sitio. Otras etiquetas de redes sociales se pueden considerar si se orientan a una red en particular y se quiere garantizar su visualización.

* [ ] **Open Graph de Facebook:** ![Low](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-low.png) Todos los tags Open Graph de Facebook (OG) se prueban y no falta ninguno o ninguno tiene información falsa. Las imágenes deben ser de al menos 600 x 315 píxeles, se recomiendan 1200 x 630 píxeles.

```html
<meta property="og:type" content="website">
<meta property="og:url" content="https://example.com/page.html">
<meta property="og:title" content="Content Title">
<meta property="og:image" content="https://example.com/image.jpg">
<meta property="og:description" content="Description Here">
<meta property="og:site_name" content="Site Name">
<meta property="og:locale" content="en_US">
```

> * 📖 [Guia para compartir para Webmasters](https://developers.facebook.com/docs/sharing/webmasters/)
> * 🛠 Prueba tu página con [Facebook OG testing](https://developers.facebook.com/tools/debug/)
 
* [ ] **Twitter Card:** ![Low](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-low.png)

```html
<meta name="twitter:card" content="summary">
<meta name="twitter:site" content="@site_account">
<meta name="twitter:creator" content="@individual_account">
<meta name="twitter:url" content="https://example.com/page.html">
<meta name="twitter:title" content="Content Title">
<meta name="twitter:description" content="Content description less than 200 characters">
<meta name="twitter:image" content="https://example.com/image.jpg">
```

> * 📖 [Empezando con Cards — Twitter Developers](https://developer.twitter.com/en/docs/tweets/optimize-with-cards/guides/getting-started)
> * 🛠 Prueba tu página con [Twitter card validator](https://cards-dev.twitter.com/validator) 

**[⬆ volver arriba](#table-of-contents)**

---
## HTML

### Las mejores prácticas

* [ ] **Elementos semánticos HTML5:** ![High](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) Elementos semánticos HTML5 son usados apropiadamente y en orden (header, section, footer, main...)

> 📖 [Referencia HTML](http://htmlreference.io/)

* [ ] **Datos estructurados:** ![High](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) Las páginas que utilizan datos estructurados se prueban y no tienen errores.

```application/ld+json
<script type="application/ld+json">
{
  "@context": "http://schema.org",
  "@type": "Organization",
  "url": "http://www.example.com",
  "name": "Unlimited Ball Bearings Corp.",
  "contactPoint": {
    "@type": "ContactPoint",
    "telephone": "+1-401-555-1212",
    "contactType": "Customer service"
  }
}
</script>
```

> 📖 [Introducción a Datos Estructurados | Search | Google Developers](https://developers.google.com/search/docs/guides/intro-structured-data)
> 🛠 Test your page with the [Structured Data Testing Tool](https://developers.google.com/structured-data/testing-tool/)

* [ ] **Páginas de Error:** ![High](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) Páginas de Error 404 y 5xx existen. Recuerde que cualquier página de error 5xx necesita tener su CSS integrado (inline). No hacer una llamada externa en el servidor actual.
* [ ] **Noopener:** ![Medium](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-medium.png) En caso de que se esté utilizando ``target = "_ blank"`` en los enlaces, ``rel = "noreferrer noopener"`` está presente en ``<img>``.
* [ ] **Clean up comments:** ![Low](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-low.png) Se debe eliminar el código innecesario antes de poner la página en producción.
  
### Pruebas HTML

* [ ] **Cumple con W3C:**: ![High](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) Todas las páginas deben probarse con el validador W3C para identificar posibles problemas en el código HTML.
 
> 🛠 [Validador W3C](https://validator.w3.org/)

* [ ] **Limpieza HTML:** ![High](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) Uso de herramientas para analizar cualquier problema que pueda tener el código HTML.

> 🛠 [Dirty markup](https://dirtymarkup.com/)

* [ ] **Browsers de escritorio:** ![High](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) Todas las páginas se probaron en todos los navegadores de escritorio modernos. (Safari, Firefox, Chrome, Internet Explorer, EDGE...).
* [ ] **Browsers móviles:**  ![High](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) Todas las páginas se probaron en todos los navegadores móviles. (Browser nativo, Chrome, Safari...).

* [ ] **Comprobación de Links:** ![High](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) No existen enlaces rotos en la página, verifique que no tiene ningún error 404.
 
> * 🛠 [W3C Link Checker](http://validator.w3.org/checklink)

* [ ] **Pruebas con Adblockers:** ![Medium](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-medium.png) Su sitio web muestra contenido correctamente aunqu se encuentre con adblockers habilitados (Puede mostrar un mensaje para animar a las personas a deshabilitar su adblocker)

- [ ] **Diseño Pixel Perfect:** ![High](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) Las páginas están cercanas a píxeles perfectos. Según la calidad del equipo creativo, puede que no sea 100% preciso, pero su página debe reflejar lo creado en su plantilla.

>  [Pixel Perfect - Chrome Extension](https://chrome.google.com/webstore/detail/perfectpixel-by-welldonec/dkaagdgjmgdmbnecmcefdhjekcoceebi?hl=en)

**[⬆ volver arriba](#table-of-contents)**

---
## Webfonts

* [ ] **Formatos Webfont:** ![High](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) WOFF, WOFF2 y TTF son compatibles con todos los navegadores modernos.
  
> * 📖 [WOFF - Web Open Font Format - Caniuse](http://caniuse.com/#feat=woff). 
> * 📖 [WOFF 2.0 - Web Open Font Format - Caniuse](http://caniuse.com/#feat=woff2).
> * 📖 [TTF/OTF - TrueType and OpenType font support](http://caniuse.com/#feat=ttf)
> * 📖 [Using @font-face - CSS-Tricks](https://css-tricks.com/snippets/css/using-font-face/)

* [ ] **Webfont size:** ![High](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) Los Webfont no pesan mas de 2 MB (todas las variantes incluidas)

**[⬆ volver arriba](#table-of-contents)**

---
## CSS

> **Notas:** Darle una mirada a [CSS guidelines](https://cssguidelin.es/) y a [Sass Guidelines](https://sass-guidelin.es/) usado por la mayoria de los desarrolladores Front-End. Si hay dudas acerca de propiedades CSS, puede revisar [CSS Reference](http://cssreference.io/).

* [ ] **Diseño Web Responsive:** ![High](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) El sitio usa diseño responsive.
* [ ] **CSS Print:** ![Medium](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-medium.png) Se proporciona una hoja de estilo especial para imprmir y su visualización es correcta en cada página.
* [ ] **Preprocesadores:** ![Medium](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-medium.png) La página usa un preprocesados CSS 
> * 📖 [Sass](http://sass-lang.com/).
> * 📖 [Less](http://lesscss.org/).
* [ ] **Unique ID:** ![High](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) Si se usan identificadores, son exclusivos de cada página del sitio.
* [ ] **Reset CSS:** ![High](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) Se utiliza un reset de CSS. *(Si utiliza un Framework CSS como Twitter Bootstrap o Foundation, ya está incluido un Normalize)*.

> * 📖 [Reset.css](https://meyerweb.com/eric/tools/css/reset/)
> * 📖 [Normalize.css](https://necolas.github.io/normalize.css/)
> * 📖 [Reboot](https://v4-alpha.getbootstrap.com/content/reboot/)

* [ ] **Prefijo JS:** ![Low](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-low.png) Todas las clases e identificadores usados por rutinas javascript tienen el prefijo **js-** y no se aplica diseño a través de CSS.

```html
<div id="js-slider" class="my-slider">
<!-- Or -->
<div id="id-used-by-cms" class="js-slider my-slider">
```

* [ ] **CSS incrustado:** ![High](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) Evitar a toda costa el uso de CSS incrustado o inline: solo se utiliza por razones muy específicas (por ejemplo, background-image para slider, CSS critico).
* [ ] **Prefijos específicos de proveedores:** ![High](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) Los prefijos CSS de proveedores se usan y se generan de acuerdo con la compatibilidad de compatibilidad de su navegador.

```
.example {
    display: -webkit-box;
    display: -ms-flexbox;
    display: flex;
    -webkit-transition: all .5s; /* vendor prefix for webkit */
    -o-transition: all .5s; /* vendor prefix for opera */
    transition: all .5s;
    -webkit-user-select: none;
       -moz-user-select: none; /* vendor prefix for mozilla */
        -ms-user-select: none;
            user-select: none;
    background: -webkit-gradient(linear, left top, left bottom, from(white), to(black));
    background: -webkit-linear-gradient(top, white, black);
    background: -o-linear-gradient(top, white, black);
    background: linear-gradient(to bottom, white, black);
}
```

> 🛠 [Autoprefixer CSS online](https://autoprefixer.github.io/)

### Rendimiento

- [ ] **Concatenación:** ![High](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) Los archivos CSS se concatenan en un único archivo *(No para HTTP/2)*
- [ ] **Minificación:** ![High](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) Todos los archivos CSS están minificados.
- [ ] **CSS no bloqueante:** ![Medium](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-medium.png) Los archivos CSS deben ser no bloqueantes para evitar que el DOM tome tiempo en cargar.

> * 📖 [loadCSS by filament group](https://github.com/filamentgroup/loadCSS)

- [ ] **CSS en desuso:** ![Low](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-low.png) Se ha quitado CSS que no se usa.

> * 🛠 [UnCSS Online](https://uncss-online.com/) 🛠
> * 🛠 [PurifyCSS](https://github.com/purifycss/purifycss)


### Pruebas CSS

* [ ] **Stylelint:** ![High](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) Todos los archivos con código CSS o SCSS no contienen errores. 

> * 🛠 [stylelint, a CSS linter](https://stylelint.io/)
> * 📖 [Sass guidelines](https://sass-guidelin.es/)

* [ ] **Diseño web Responsive:** ![High](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png)todas las páginas sin testeadas exitosamente en las siguientes dimensiones de quiebre: 320px, 768px, 1024px (lista que se puede ajustar a las necesidades del proyecto).

* [ ] **Validador CSS:** ![Medium](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-medium.png) El CSS fue probado y se corrigieron todos los errores del caso.

> 🛠 [Validador CSS](http://jigsaw.w3.org/css-validator/)

* [ ] **Depuración CSS:** ![Low](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-low.png) paginas fueron probadas con DebugCSS

> 🛠 [Debug CSS](http://yahoo.github.io/debugCSS)

* [ ] **Dirección de lectura:** ![High](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) En caso de ser requerido, todas las paginas deben ser probadas con lenguajes RTL o LTR.

**[⬆ volver arriba](#table-of-contents)**

---
## Imágenes

> **Notas:** Puede consulta el ebook gratuito de Addy Osmani para una mejor compresión de esta sección **[Essential Image Optimization](https://images.guide/)** 

### Buenas prácticas
* [ ] **Optimización:** ![High](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) Todas las imágenes están optimizadas para ser renderizadas en navegadores. El formato WebP se puede usar para páginas críticas (como Homepage).

> * 🛠 [Imagemin](https://github.com/imagemin/imagemin)
> * 🛠 Usar [ImageOptim](https://imageoptim.com/) para optimizar imágenes de forma gratuita.

* [ ] **Retina:** ![Low](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-low.png) Se proporcionan imágenes de diseño x2 y se admite pantalla retina.

* [ ] **Sprite:** ![Medium](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-medium.png) Las imágenes pequeñas están en un archivo de sprite (en el caso de los iconos, pueden estar en una imagen sprite en formato SVG).

* [ ] **Alto y Ancho:** ![High](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) Todos ``<img>`` tienen alto y ancho establecidos (No especifica píxeles o porcentaje).

> ***Nota:*** Muchos desarrolladores suponen que el ancho y la altura no son compatibles con el diseño web responsive. No es el caso en lo absoluto.

* [ ] **Texto Alternativo:** ![High](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) Todas las etiquetas ``<img>`` tienen definido el texto alternativo que describe la imagen visualmente. 

```img
<img src="image.png" alt="Descripción del contenido de la imágen">
```

* [ ] **Carga Lazy:** ![Medium](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-medium.png) Las imágenes se cargan en demanda (lazyloaded) a medida que van apareciendo en pantalla y no antes (Siempre se proporciona una alternativa para el caso noscript).

**[⬆ volver arriba](#table-of-contents)**

---
## JavaScript

### Buenas prácticas

* [ ] **JavaScript Inline:** ![High](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) No tiene ningún código JavaScript inline (mezclado entre el código HTML).
* [ ] **Concatenación:** ![High](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) Los archivos JavaScript están concatenados.
* [ ] **Minificación:** ![High](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) Los archivos JavaScript están minificados (es valioso agregar el sufijo ``.min.js``).

> [Minify Resources (HTML, CSS, and JavaScript)](https://developers.google.com/speed/docs/insights/MinifyResources)

* [ ] **Javascript no bloqueante:** ![Medium](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-medium.png) Los archivos JavaScript se cargan de forma asincrónica con ``async`` o se difieren su carga mediante el atributo ``defer``.

> 📖 [Quitar el JavaScript que bloquea el render](https://developers.google.com/speed/docs/insights/BlockingJS)

* [ ] **Modernizr:** ![Low](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-low.png) Si necesita usar algunas características específicas del navegador, puede usar un Modernizr.

> 🛠 [Personalizar Modernizr](https://modernizr.com/download?setclasses)

### Pruebas JavaScript

* [ ] **ESLint:** ![High](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) ESLint no marca ningún error (según las reglas de configuración o estándares)

**[⬆ volver arriba](#table-of-contents)**

---
## Rendimiento

### Buenas prácticas

- [ ] **Tamaño de la página (peso):** ![High](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) El peso de cada página está entre 0kb y 500kb.

> * 🛠 [Website Page Analysis](https://tools.pingdom.com)
> * 📖 [Size Limit: Make the Web lighter](https://evilmartians.com/chronicles/size-limit-make-the-web-lighter)

- [ ] **Minified:** ![Medium](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-medium.png) El HTML está miníficado
> 🛠 [Validador W3C](http://validator.w3.org/)
 
* [ ] **Carga Lazy:** ![Medium](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-medium.png) Las imágenes, scripts y CSS deben cargarse de forma diferida para mejorar el tiempo de respuesta de la página actual (revise los detalles en las respectivas secciones anteriores).

### Pruebas de rendimiento

* [ ] **Google PageSpeed:** ![High](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) Todas sus páginas fueron evaluadas (y no solo la página de inicio) y tienen puntuación entre 90 y 100.

> * 🛠 [Google PageSpeed](https://developers.google.com/speed/pagespeed/insights/)
> * 🛠 [Test your mobile speed with Google](https://testmysite.withgoogle.com)
> * 🛠 [WebPagetest - Website Performance and Optimization Test](https://www.webpagetest.org/)

**[⬆ volver arriba](#table-of-contents)**

---
## Accesibilidad

> **Notas:** Revise la video playlist [A11ycasts with Rob Dodson](https://www.youtube.com/playlist?list=PLNYkxOF6rcICWx0C9LVWWVqvHlYJyqw7g) 📹

### Buenas prácticas

- [ ] **Mejora Progresiva:** ![Medium](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-medium.png) Las funcionalidades principales, como la navegación principal y la búsqueda, funciona sin JavaScript habilitado.

> 📖 [Enable / Disable JavaScript in Chrome Developer Tools](https://www.youtube.com/watch?v=kBmvq2cE0D8)

- [ ] **Contrastes de Color:** ![Medium](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-medium.png) El contraste de color debería pasar al menos WCAG AA (debe pasar AAA para dispositivos móviles)

> 🛠 [Contrast ratio](http://leaverou.github.io/contrast-ratio/)

#### Encabezados

* [ ] **H1:** ![High](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) Todas las páginas tienen un H1 que no es el título del sitio web.
* [ ] **Headings:** ![High](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) Los títulos deben usarse correctamente en el orden correcto (H1 a H6)

> 📹 [Por qué los encabezados y los puntos de referencia son tan importantes -- A11ycasts #18](https://www.youtube.com/watch?v=vAAzdi1xuUY&index=9&list=PLNYkxOF6rcICWx0C9LVWWVqvHlYJyqw7g)

#### Landmarks

- [ ] **Role banner:** ![High](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) ``<header>`` contiene ``role="banner"``
- [ ] **Role navigation:** ![High](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) ``<nav>`` contiene ``role="navigation"``
- [ ] **Role main:** ![High](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) ``<main>`` contiene ``role="main"``

> 📖 [Using ARIA landmarks to identify regions of a page](https://www.w3.org/WAI/GL/wiki/Using_ARIA_landmarks_to_identify_regions_of_a_page)

### Semántica

- [ ] **Se usan mecanismos de entrada propios de HTML5:** Esto es importante en dispositivos móviles que muestran teclados y widgets personalizados para los diferentes tipos.

> 📖 [tipos de entrada en Moviles](http://mobileinputtypes.com/)

### Formulario
* [ ] **Label:** ![High](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) Una etiqueta está asociada con un elemento de formulario de entrada. En caso de que una etiqueta no pueda mostrarse, use ``aria-label`` en su lugar.

> 📖 [Using the aria-label attribute - MDN](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/ARIA_Techniques/Using_the_aria-label_attribute)

### Pruebas de Accesibilidad
* [ ] **Pruebas Estándares de Accesibilidad:** ![High](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) Use la herramienta WAVE para comprobar si su página respeta los estándares de accesibilidad.


> 🛠 [Pruebas Wave](http://wave.webaim.org/)

* [ ] **Navegación con teclado:** ![High](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) Pruebe su sitio web usando solo el teclado en un orden previsible. Todos los elementos interactivos son alcanzables y utilizables.

* [ ] **Screen-reader:** ![Medium](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-medium.png) Todas las páginas se probaron exitosamente en un lector de pantalla (VoiceOver, ChromeVox, NVDA o Lynx).

* [ ] **Focus style:** ![High](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) Si el foco está desactivado, se reemplaza por un estado visible en CSS.

> 📹 [Managing Focus - A11ycasts #22](https://www.youtube.com/watch?v=srLRSQg6Jgg&index=5&list=PLNYkxOF6rcICWx0C9LVWWVqvHlYJyqw7g)

**[⬆ volver arriba](#table-of-contents)**

---
## SEO

* [ ] **Google Analytics:** ![High](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) Google Analytics está instalado y configurado correctamente.
* [ ] **Lógica de los Encabezados:** ![Medium](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-medium.png) El texto puesto en los encabezados ayuda a comprender el contenido de la página actual.
* [ ] **sitemap.xml:** ![High](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) Existe un sitemap.xml que se envió en Google Search Console (por ejemplo: Google Webmaster Tools)
* [ ] **robots.txt:** ![High](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) El archivo robots.txt no está bloqueando páginas web
Enlace el sitio a Google webmaster tools
* [ ] **Sitemap HTML:** ![Medium](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-medium.png) Se proporciona un mapa del sitio en formato HTML y éste se puede acceder a través de un enlace puesto en el footer de su sitio web.

**[⬆ volver arriba](#table-of-contents)**

---
## Contributing

**Open an issue or a pull request to suggest changes or additions.**

### Guide

The **Front-End Checklist** repository consists of two branches:

#### 1. `master`

This branch consists of the `README.md` file that is automatically reflected on the [Front-End Checklist](http://frontendchecklist.com/) website.

#### 2. `develop`

This branch will be used to make some significant changes to the structure, content if needed. It is preferable to use the master branch to fix small errors or add a new item.

### Contributors

Check out all the super awesome [contributors](https://github.com/thedaviddias/frontendchecklist/graphs/contributors).

## Authors

**[David Dias]()**, **[Geoffrey Signorato](https://github.com/geosenna)**, **[Sandeep Ramgolam](https://twitter.com/__Sun__)** and **[Cédric Poilly](https://github.com/CedricPoilly)**.

## License

[![CC0](http://i.creativecommons.org/p/zero/1.0/88x31.png)](https://creativecommons.org/publicdomain/zero/1.0/)

**[⬆ back to top](#table-of-contents)**







