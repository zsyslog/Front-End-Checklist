# Front-End Checklist
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
6. **[Imagenes](#images)**
7. **[JavaScript](#javascript)**
8. **[Rendimiento](#performance)**
9. **[Accesibilidad](#accessibility)**
10. **[SEO](#seo)**

## ¿Como usar?

Todos los elementos de la **Checklist Front-End** son necesarios para la mayoría de los proyectos, pero algunos elementos pueden omitirse o no ser esenciales (en el caso de una aplicación web de administración, es posible que no necesite un feed RSS, por ejemplo). Elegimos utilizar 3 niveles de flexibilidad:

* ![Low](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-low.png) quiere decir que es **recomendado** pero puede ser emitido en caso particulares.
* ![Medium](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-medium.png) quiere decir que es **altamente recomendado** y puede ser omitido en casos muy particulares. Algunos elementos, si son omitidos por algún motivo, pueden tener repercusiones negativas en el rendimiento o en el SEO.
* ![High](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) quiere decir que **no puede ser omitido** por ningún motivo. Podría causar un mal funcionamiento de la página o tener problemas de rendimiento o SEO. Las prioridades de pruebas deben ponerse acá.

Algunos recursos poseen un ícono para ayudar a comprender qué tipo de contenido / ayuda puede encontrar en la lista de verificación

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

* [ ] **X-UA-Compatible:** ![Medium](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-medium.png) El X-UA-Compatible meta tag está presente.
 
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
* [ ] **Language tag:** ![High](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) The language tag of your website is specified and related to the language of the current page.

```html
<html lang="en">
```

* [ ] **Direction tag:** ![Medium](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-medium.png) The direction of lecture is specified on the body tag (It can be used on another HTML tag).

```html
<html dir="rtl">
```

> 📖 [dir - HTML | MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/dir)

* [ ] **Alternate language:** ![Low](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-low.png) The language tag of your website is specified and related to the language of the current page.

```html
<link rel="alternate" href="https://es.example.com/" hreflang="es">
```

* [ ] **Conditional comments:** ![Low](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-low.png) Conditional comments are present for IE if needed.

> 📖 [About conditional comments (Internet Explorer) - MSDN - Microsoft](https://msdn.microsoft.com/en-us/library/ms537512(v=vs.85).aspx)

* [ ] **RSS feed:** ![Low](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-low.png) If your project is a blog or has articles, an RSS link was provided.

* [ ] **CSS Critical:** ![Medium](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-medium.png) The CSS critical (or "above the fold") collects all the CSS used to render the visible portion of the page. It is embedded before your principal CSS call and between ``<style></style>`` in a single line (minified).

> 🛠 [Critical by Addy Osmany on Github](https://github.com/addyosmani/critical)

* [ ] **CSS order:** ![High](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) All CSS files are loaded before any JavaScript files in the ``<head>``. (Except the case, where sometimes JS files are loaded asynchronously on top of your page).

### Social meta

***Facebook OG*** and ***Twitter Cards*** are, for any website, highly recommended. The other social media tags can be considered if you target a particular presence on those and want to ensure the display.

* [ ] **Facebook Open Graph:** ![Low](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-low.png) All Facebook Open Graph (OG) are tested and no one is missing or with a false information. Images need to be at least 600 x 315 pixels, 1200 x 630 pixels recommended.

```html
<meta property="og:type" content="website">
<meta property="og:url" content="https://example.com/page.html">
<meta property="og:title" content="Content Title">
<meta property="og:image" content="https://example.com/image.jpg">
<meta property="og:description" content="Description Here">
<meta property="og:site_name" content="Site Name">
<meta property="og:locale" content="en_US">
```

> * 📖 [A Guide to Sharing for Webmasters](https://developers.facebook.com/docs/sharing/webmasters/)
> * 🛠 Test your page with the [Facebook OG testing](https://developers.facebook.com/tools/debug/)
 
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

> * 📖 [Getting started with cards — Twitter Developers](https://developer.twitter.com/en/docs/tweets/optimize-with-cards/guides/getting-started)
> * 🛠 Test your page with the [Twitter card validator](https://cards-dev.twitter.com/validator) 

**[⬆ back to top](#table-of-contents)**

---
## HTML

### Best practices

* [ ] **HTML5 Semantic Elements:** ![High](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) HTML5 Semantic Elements are used appropriately (header, section, footer, main...)

> 📖 [HTML Reference](http://htmlreference.io/)

* [ ] **Structured Data:** ![High](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) Pages using structured data are tested and are without errors.

> 📖 [Introduction to Structured Data | Search | Google Developers](https://developers.google.com/search/docs/guides/intro-structured-data)
> 🛠 Test your page with the [Structured Data Testing Tool](https://developers.google.com/structured-data/testing-tool/)

* [ ] **Error pages:** ![High](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) Error 404 page and 5xx exist. Remember that the 5xx error page needs to have his CSS integrated (no external call on the current server).
* [ ] **Noopener:** ![Medium](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-medium.png) In case you are using ``target="_blank"`` on your links, ``rel="noreferrer noopener"`` is present on the ``<img>``.
* [ ] **Clean up comments:** ![Low](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-low.png) Unnecessary code needs to be removed before sending the page to production.
  
### HTML testing

* [ ] **W3C compliant:**: ![High](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) All pages need to be tested with the W3C validator to identify possible issues in the HTML code.
 
> 🛠 [W3C validator](https://validator.w3.org/)

* [ ] **HTML Lint:** ![High](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) I use tools to help me analyze any issues I could have on my HTML code.

> 🛠 [Dirty markup](https://dirtymarkup.com/)

* [ ] **Desktop Browsers:** ![High](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) All pages were tested on all current desktop browsers (Safari, Firefox, Chrome, Internet Explorer, EDGE...).
* [ ] **Mobile Browsers:**  ![High](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) All pages were tested on all current mobile browsers (Native browser, Chrome, Safari...).

* [ ] **Link checker:** ![High](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) There are no broken links in my page, verify that you don't have any 404 error.
 
> * 🛠 [W3C Link Checker](http://validator.w3.org/checklink)

* [ ] **Adblockers test:** ![Medium](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-medium.png) Your website shows your content correctly with adblockers enabled (You can provide a message encouraging people to disable their adblocker)

- [ ] **Pixel perfect:** ![High](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) Pages are close to pixel perfect. Depending on the quality of the creatives, you may not be 100% accurate, but your page needs to be close to your template.

>  [Pixel Perfect - Chrome Extension](https://chrome.google.com/webstore/detail/perfectpixel-by-welldonec/dkaagdgjmgdmbnecmcefdhjekcoceebi?hl=en)

**[⬆ back to top](#table-of-contents)**

---
## Webfonts

* [ ] **Webfont format:** ![High](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) WOFF, WOFF2 and TTF are supported by all modern browsers.
  
> * 📖 [WOFF - Web Open Font Format - Caniuse](http://caniuse.com/#feat=woff). 
> * 📖 [WOFF 2.0 - Web Open Font Format - Caniuse](http://caniuse.com/#feat=woff2).
> * 📖 [TTF/OTF - TrueType and OpenType font support](http://caniuse.com/#feat=ttf)
> * 📖 [Using @font-face - CSS-Tricks](https://css-tricks.com/snippets/css/using-font-face/)

* [ ] **Webfont size:** ![High](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) Webfont sizes don't exceed 2 MB (all variants included)

**[⬆ back to top](#table-of-contents)**

---
## CSS

> **Notes:** Take a look on [CSS guidelines](https://cssguidelin.es/) and [Sass Guidelines](https://sass-guidelin.es/) followed by most  Front-End developers. If you have a doubt on CSS properties, you can visit [CSS Reference](http://cssreference.io/).

* [ ] **Responsive Web Design:** ![High](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) The website is using responsive web design.
* [ ] **CSS Print:** ![Medium](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-medium.png) A print stylesheet is provided and is correct on each page.
* [ ] **Preprocessors:** ![Medium](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-medium.png) Your page is using a CSS preprocessor ([Sass](http://sass-lang.com/) is preferred).
* [ ] **Unique ID:** ![High](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) If IDs are used, they are unique to a page
* [ ] **Reset CSS:** ![High](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) A CSS reset (reset, normalize or reboot) is used and up to date. *(If you are using a CSS Framework like Twitter Bootstrap or Foundation, a Normalize is already included into it.)*

> * 📖 [Reset.css](https://meyerweb.com/eric/tools/css/reset/)
> * 📖 [Normalize.css](https://necolas.github.io/normalize.css/)
> * 📖 [Reboot](https://v4-alpha.getbootstrap.com/content/reboot/)

* [ ] **JS prefix:** ![Low](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-low.png) All classes (or id- used in JavaScript files) begin with **js-** and are not styled into the CSS files.

```html
<div id="js-slider" class="my-slider">
<!-- Or -->
<div id="id-used-by-cms" class="js-slider my-slider">
```

* [ ] **CSS embed or line:** ![High](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) Avoid at all cost the use of CSS embed or inline: only used for valid reasons (ex: background-image for slider, CSS critical).
* [ ] **Vendor prefixes:** ![High](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) CSS vendor prefixes are used and are generated accordingly with your browser support compatibility.

> 🛠 [Autoprefixer CSS online](https://autoprefixer.github.io/)

### Performance

- [ ] **Concatenation:** ![High](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) CSS files are concatenated in a single file *(Not for HTTP/2)*
- [ ] **Minification:** ![High](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) All CSS files are minified.
- [ ] **Non-blocking:** ![Medium](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-medium.png) CSS files need to be non-blocking to prevent the DOM from taking time to load.

> * 📖 [loadCSS by filament group](https://github.com/filamentgroup/loadCSS)

- [ ] **Unused CSS:** ![Low](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-low.png) Remove unused CSS

> * 🛠 [UnCSS Online](https://uncss-online.com/) 🛠
> * 🛠 [PurifyCSS](https://github.com/purifycss/purifycss)


### CSS testing

* [ ] **Stylelint:** ![High](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) All CSS or SCSS files are without any errors. 

> * 🛠 [stylelint, a CSS linter](https://stylelint.io/)
> * 📖 [Sass guidelines](https://sass-guidelin.es/)

* [ ] **Responsive web design:** ![High](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) All pages were tested at the following breakpoints: 320px, 768px, 1024px (can be more / different according to your analytics).

* [ ] **CSS Validator:** ![Medium](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-medium.png) The CSS was tested and pertinent errors were corrected.

> 🛠 [CSS Validator](http://jigsaw.w3.org/css-validator/)

* [ ] **Debug CSS:** ![Low](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-low.png) Pages were tested with DebugCSS

> 🛠 [Debug CSS](http://yahoo.github.io/debugCSS) (you can use the bookmarklet)

* [ ] **Reading direction:** ![High](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) All pages need to be tested for LTR and RTL languages if they need to be supported.

**[⬆ back to top](#table-of-contents)**

---
## Images

> **Notes:** For a complete understanding of image optimization, check the free ebook **[Essential Image Optimization](https://images.guide/)** from Addy Osmani.

### Best practices
* [ ] **Optimization:** ![High](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) All images are optimized to be rendered in the browser. WebP format could be used for critical pages (like Homepage).

> * 🛠 [Imagemin](https://github.com/imagemin/imagemin)
> * 🛠 Use [ImageOptim](https://imageoptim.com/) to optimise your images for free.

* [ ] **Retina:** ![Low](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-low.png) You provide layout images x2 or 3x, support retina display.
* [ ] **Sprite:** ![Medium](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-medium.png) Small images are in a sprite file (in case of icons, they can be in an SVG sprite image).
* [ ] **Width and Height:** ![High](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) All ``<img>`` have height and width set (Don't specify px or %).

> ***Note:*** Lots of developers assume that width and height are not compatible with responsive web design. It's absolutely not the case.

* [ ] **Alternative text:** ![High](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) All ``<img>`` have an alternative text which describe the image visually.
* [ ] **Lazy loading:** ![Medium](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-medium.png) Images are lazyloaded (A noscript fallback is always provided).

**[⬆ back to top](#table-of-contents)**

---
## JavaScript

### Best practices

* [ ] **JavaScript Inline:** ![High](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) You don't have any JavaScript code inline (mixed with your HTML code).
* [ ] **Concatenation:** ![High](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) JavaScript files are concatenated.
* [ ] **Minification:** ![High](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) JavaScript files are minified (you can add the ``.min`` suffix).

> [Minify Resources (HTML, CSS, and JavaScript)](https://developers.google.com/speed/docs/insights/MinifyResources)

* [ ] **Non-blocking:** ![Medium](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-medium.png) JavaScript files are loaded asynchronously using ``async`` or deferred using ``defer`` attribute.

> 📖 [Remove Render-Blocking JavaScript](https://developers.google.com/speed/docs/insights/BlockingJS)

* [ ] **Modernizr:** ![Low](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-low.png) If you need to target some specific features you can use a custom Modernizr to add classes in your ``<html>`` tag.

> 🛠 [Customize your Modernizr](https://modernizr.com/download?setclasses)

### JavaScript testing

* [ ] **ESLint:** ![High](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) No errors are flagged by ESLint (based on your configuration or standards rules)

**[⬆ back to top](#table-of-contents)**

---
## Performance

### Best practices

- [ ] **Weight page:** ![High](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) The weight of each page is between 0kb and 500kb

> * 🛠 [Website Page Analysis](https://tools.pingdom.com)
> * 📖 [Size Limit: Make the Web lighter](https://evilmartians.com/chronicles/size-limit-make-the-web-lighter)

- [ ] **Minified:** ![Medium](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-medium.png) Your HTML is minified
> 🛠 [W3C Validator](http://validator.w3.org/)
 
* [ ] **Lazy loading:** ![Medium](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-medium.png) Images, scripts and CSS need to be lazy loaded to improve the response time of the current page (See details in their respective sections).

### Performance testing

* [ ] **Google PageSpeed:** ![High](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) All your pages were tested (not only the homepage) and have min 90/100.

> * 🛠 [Google PageSpeed](https://developers.google.com/speed/pagespeed/insights/)
> * 🛠 [Test your mobile speed with Google](https://testmysite.withgoogle.com)
> * 🛠 [WebPagetest - Website Performance and Optimization Test](https://www.webpagetest.org/)

**[⬆ back to top](#table-of-contents)**

---
## Accessibility

> **Notes:** You can watch the playlist [A11ycasts with Rob Dodson](https://www.youtube.com/playlist?list=PLNYkxOF6rcICWx0C9LVWWVqvHlYJyqw7g) 📹

### Best practices

- [ ] **Progressive enhancement:** ![Medium](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-medium.png) Major functionality like main navigation and search should work without JavaScript enabled.

> 📖 [Enable / Disable JavaScript in Chrome Developer Tools](https://www.youtube.com/watch?v=kBmvq2cE0D8)

- [ ] **Color contrast:** ![Medium](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-medium.png) Color contrast should at least pass WCAG AA (AAA for mobile)

> 🛠 [Contrast ratio](http://leaverou.github.io/contrast-ratio/)

#### Headings

* [ ] **H1:** ![High](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) All pages have an H1 which is not the title of the website.
* [ ] **Headings:** ![High](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) Headings should be used properly in the right order (H1 to H6)

> 📹 [Why headings and landmarks are so important -- A11ycasts #18](https://www.youtube.com/watch?v=vAAzdi1xuUY&index=9&list=PLNYkxOF6rcICWx0C9LVWWVqvHlYJyqw7g)

#### Landmarks

- [ ] **Role banner:** ![High](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) ``<header>`` has ``role="banner"``
- [ ] **Role navigation:** ![High](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) ``<nav>`` has ``role="navigation"``
- [ ] **Role main:** ![High](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) ``<main>`` has ``role="main"``

> 📖 [Using ARIA landmarks to identify regions of a page](https://www.w3.org/WAI/GL/wiki/Using_ARIA_landmarks_to_identify_regions_of_a_page)

### Semantics

- [ ] **Specific HTML5 input types are used:** This is especially important for mobile devices that show customized keypads and widgets for different types.

> 📖 [Mobile Input Types](http://mobileinputtypes.com/)

### Form
* [ ] **Label:** ![High](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) A label is associated with each input form element. In case, a label can't be display, use ``aria-label`` instead.

> 📖 [Using the aria-label attribute - MDN](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/ARIA_Techniques/Using_the_aria-label_attribute)

### Accessibility testing
* [ ] **Accessibility standards testing:** ![High](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) Use the WAVE tool to test if your page respects the accessibility standards.

> 🛠 [Wave testing](http://wave.webaim.org/)

* [ ] **Keyboard navigation:** ![High](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) Test your website using only your keyboard in a previsible order. All interactive elements are reachable and usable.
* [ ] **Screen-reader:** ![Medium](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-medium.png) All pages were tested in a screen-reader (VoiceOver, ChromeVox, NVDA or Lynx).
* [ ] **Focus style:** ![High](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) If the focus is disabled, it is replaced by visible state in CSS.

> 📹 [Managing Focus - A11ycasts #22](https://www.youtube.com/watch?v=srLRSQg6Jgg&index=5&list=PLNYkxOF6rcICWx0C9LVWWVqvHlYJyqw7g)

**[⬆ back to top](#table-of-contents)**

---
## SEO

* [ ] **Google Analytics:** ![High](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) Google Analytics is installed and correctly configured.
* [ ] **Headings logic:** ![Medium](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-medium.png) Heading text helps to understand the content in the current page.
* [ ] **sitemap.xml:** ![High](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) A sitemap.xml exists and was submit in Google Search Console (ex:Google Webmaster Tools)
* [ ] **robots.txt:** ![High](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) The robots.txt is not blocking webpages
Link your website to the Google webmaster tools
* [ ] **Sitemap HTML:** ![Medium](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-medium.png) An HTML sitemap is provided and is accessible via a link in the footer of your website.

**[⬆ back to top](#table-of-contents)**

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







