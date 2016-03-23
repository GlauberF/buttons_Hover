# Hover.css

Uma coleção de CSS3 efeitos de foco , botões, logotipos, SVG, contou com imagens e assim por diante. Facilmente aplicar aos seus próprios elementos, modificar ou simplesmente usar como inspiração. Disponível em CSS, Sass, e menos.


## Download / Instalação

- NPM: `NPM instalar hover.css` --save
- Bower: `pavilhão instalar Hover`
- [Download Zip] (https://github.com/IanLunn/Hover/archive/master.zip)

## Como usar
Hover.css pode ser utilizado num certo número de maneiras; , copie e cole o efeito que você gostaria de usar em seu próprio estilo ou fazer referência a folha de estilo. Em seguida, basta adicionar o nome da classe do efeito para o elemento que você gostaria que fosse aplicado.

### A. Copiar e colar um Efeito
Se você está pensando em usar apenas um ou vários efeitos, é melhor prática para copiar e colar um efeito em seu próprio estilo, para que um usuário não precisa baixar `css / hover.css` na sua totalidade.

Supondo que você quer usar o efeito de crescer:

1. Faça o download Hover.css
2. Em `css/hover.css`, encontrar o CSS Grow (cada efeito é nomeado usando um comentário acima):

    ```css
    /* Grow */
    .hvr-grow {
        display: inline-block;
        vertical-align: middle;
        transform: translateZ(0);
        box-shadow: 0 0 1px rgba(0, 0, 0, 0);
        backface-visibility: hidden;
        -moz-osx-font-smoothing: grayscale;
        transition-duration: 0.3s;
        transition-property: transform;
    }

    .hvr-grow:hover,
    .hvr-grow:focus,
    .hvr-grow:active {
        transform: scale(1.1);
    }
    ```
3. Copie este efeito e, em seguida, colá-lo em seu próprio estilo.
4. No arquivo HTML que você gostaria que o efeito a aparecer, adicione a classe de `.hvr-grow` no seu elemento escolhido.

Exemplo de elemento antes de aplicar efeito Hover.css:

```html
<a href="#">Adicionar</a>
```

Exemplo de elemento após a aplicação de efeito Hover.css:

```html
<a href="#" class="hvr-grow">Adicionar</a>
```

** Nota **: A partir de `2.0.0` todos os nomes de classe Hover.css são prefixados com` HVR-`para evitar conflitos com outras bibliotecas / folhas de estilo. Se estiver usando Sass / MENOS, isso pode facilmente ser mudado usando o `$ nameSpace` /` @ nameSpace` variável em `SCSS / options.scss` ou` less / _options.less`.

### B. Hover.css - Referência

Se você planeja usar muitos efeitos Hover.css, você pode gostar de fazer referência toda a folha de estilo Hover.css.

1. Download
2. adiciona `hover-min.css` para arquivos do seu site, em um diretório chamado `css` por exemplo.
3. Referencie `hover-min.css` en `<head>` da página HTML que você gostaria de adicionar efeitos Hover.css a:
```html
<head>
	<link href="css/hover-min.css" rel="stylesheet">
</head>
```
Alternativamente, você pode adicionar uma referência a uma folha de estilo existente assim (isso pode ser útil para os usuários do WordPress que são incapazes de editar HTML):
```css
@import url("hover-min.css");
```
4. Supondo que você quer usar o efeito Grow, no arquivo HTML que você gostaria de usar esse efeito, adicione a classe de `.hvr-grow` no seu elemento escolhido.

Examplo elemento depois de aplicado o efeito Hover.css:

```html
<a href="#" class="button">Adicionar</a>
```

Example element after applying Hover.css effect:

```html
<a href="#" class="button hvr-grow">Add to Basket</a>
```

### A Note on the `display` Property

To make an element "transformable", Hover.css  gives the following to all elements it is applied to:

```css
display: inline-block;
vertical-align: middle;
```

Should you wish to override this behavior, either remove the above CSS from Hover.css or change the `display` property for the element. Be sure to declare the override after the Hover.css declarations so the CSS cascade will take effect. Alternatively, if you are using the Sass/LESS version of Hover.css, you can remove/comment out the `forceBlockLevel()` mixin found in `scss/_hacks.scss` or `less/_hacks.less`.

For more information about Transformable elements, see the [CSS Transforms Module](http://www.w3.org/TR/css3-transforms/#transformable-element).

### Using FontAwesome with Icon Effects

Hover.css uses [FontAwesome](https://fortawesome.github.io/Font-Awesome/) for its icon effects. For these effects to work, a reference to the FontAwesome stylesheet must be added by placing the following in the `<head></head>` of your web page:

```html
<link href="//maxcdn.bootstrapcdn.com/font-awesome/4.2.0/css/font-awesome.min.css" rel="stylesheet" media="all">
```

Hover.css icons are added to elements via the `:before` pseudo-element. Let's take the Icon Forward effect as an example (browser prefixes and additional styles removed for brevity):

```css
.hvr-icon-forward:before {
    content: "\f138";
    position: absolute;
    right: 1em;
    padding: 0 1px;
    font-family: FontAwesome;
    transform: translateZ(0);
    transition-duration: 0.1s;
    transition-property: transform;
    transition-timing-function: ease-out;
}
```

What's important in the above example are the `font-family` and `content` declarations. `font-family: FontAwesome` tells the browser we want to use a FontAwesome icon in this pseudo-element, and the `content` value says which one. Should you wish to change the icon, change the value of the `content` property. A [full list of the values and the icon they represent can be found here](http://astronautweb.co/snippet/font-awesome/#font-awesome-list).

If you'd rather not tamper with Hover.css itself, you can override the default content value simply by declaring the same declaration again (providing it be declared after the default one either in Hover.css or another stylesheet):

```css
.hvr-icon-forward:before {
    content: "\f001";
}
```

The Icon Forward effect will then display a musical note that moves forward when hovered over (instead of the default arrow in a circle).

## What's Included?

The project consists of the following folders and files:

### css

- **demo-page.css** - Contains styles to demonstrate Hover. Not required in your projects
- **hover-min.css** - The minified/production version of Hover.css
- **hover.css** - The development version of Hover.css

### scss/less

- **effects** - Contains each individual effect sorted into categorized folders
- **_hacks.scss/_hacks.less, _mixins.scss/_mixins.less, _options.scss/_options.less** - Sass/LESS Utilities
- **hover.scss/hover.less** - Development version of Hover.css in Sass and LESS flavours

### Other

Other files of note include:

- **index.html** - Demonstrates all Hover.css effects
- **Gruntfile.js** - Used for [development of Hover.css via Grunt](#using-grunt-for-development).

## Browser Support
Many Hover.css effects rely on CSS3 features such as transitions, animations, transforms and pseudo-elements, for that reason, effects may not fully work in older browsers.

- [Transitions](http://caniuse.com/#search=transitions) and [Animations](http://caniuse.com/#search=animations) - not supported below Internet Explorer 9
- [Transforms](http://caniuse.com/#search=transforms) - not supported below Internet Explorer 10
- [Generated Content (pseudo-elements)](http://caniuse.com/#search=pseudo-elements) - not supported below Internet Explorer 8

Aside from the above mentioned browsers, Hover.css is supported across all major browsers. Please see [caniuse.com](http://caniuse.com/) for full support for many web technologies and test your webpages accordingly. It is recommended to apply fallback effects for older browsers, using CSS supported by those browsers or a feature testing library such as [Modernizr](http://modernizr.com/).

## Using Grunt for Development

Grunt is non-essential but can speed up development. With [Grunt installed](http://gruntjs.com/getting-started), run `grunt` from the command line to set up a development server accessed at [http://127.0.0.1:8000/](http://127.0.0.1:8000/). With Grunt running, Sass or LESS will be preprocessed (depending on whether you work out of the `scss` or `less` folder) and CSS files will be minified.

**Note:** Originally Grunt was set up to autoprefix CSS properties but to make the project as accessible as possible, this is no longer the case. The `prefixed(property, value)` Sass/LESS mixin should be used for browser prefixing instead. See [Using Sass/LESS for Development](#using-sassless-for-development) and [Using LESS for Development].

## Using Sass/LESS for Development

Sass/LESS are non-essential but can speed up development. Preprocess Sass/LESS with your favourite software or the environment provided via [Grunt](#using-grunt-for-development).

Sass/LESS is used in the Hover.css project to separate various CSS into specific files. Each effect is within its own file in the `effects` directory. Hover.css also uses the following `.scss` and `.less` files:

### _hacks
Contains hacks (undesirable but usually necessary lines of code) applied to certain effects. [Hacks explained here](https://github.com/IanLunn/Hover/wiki/Hacks-Explained).

### _mixins
Contains `prefixed` and `keyframes` mixins that apply the necessary prefixes you specify in `_options.scss` / `_options.less` to properties and keyframes.

Properties can be prefixed like so:

- Sass:
```css
@include prefixed(transition-duration, .3s);
```
- LESS:
```css
.prefixed(transition-duration, .3s);
```

The `prefixed` mixin is passed the property you want to prefix, followed by its value.

Keyframes can be prefixed like so:

- Sass:
```css
@include keyframes(my-animation) {
    to {
        color: red;
    }
}
```
The `keyframes` mixin is passed the keyframe name, followed by the content using the @content directive.


- LESS:
```css
.keyframes(my-animation, {
    to {
        color: red;
    }
});
```
The `keyframes` mixin is passed the keyframe name, followed by the content, both as arguments.


### _options
Contains default options, various effect options and the browser prefixes you'd like to use with the `prefixed` mixin. By default, only the `-webkit-` prefix is set to `true` (due to most browsers not requiring prefixes now).

As of `2.0.0`, `_options` also includes a `$nameSpace` / `@nameSpace` option which allows you to change the name all classes are prefixed with. The default namespace is `hvr`.

The `$includeClasses` / `@includeClasses` option by default is set to `true` and will generate all Hover.css effects under their own class names, `hvr-grow` for example. Should you wish to add the properties that make up Hover.css effects to your own class names, set this option to `false`.

## Contribute to Hover.css

If you'd like to contribute your own effects, please see the [Contributing Guide](https://github.com/IanLunn/Hover/blob/master/CONTRIBUTING.md).

## License
Hover.css is open source, and made available under a [MIT License](http://www.opensource.org/licenses/mit-license.php). Distribute, use as-is, or modify to your liking in personal and commercial projects. Please retain the original readme and license files.

Retaining the author information at the top of `css/hover.css` and placing it on your credits page or humans.txt is much appreciated.

## Hire Ian Lunn

[Ian Lunn](http://ianlunn.co.uk) is a Freelance Front-end Developer and author of [CSS3 Foundations](http://css3foundations.com/).

Hire [Ian](http://ianlunn.co.uk) for responsive websites, WordPress websites, JavaScript, animation, and optimization.

## Support Future Development

To support the future development of Hover.css and other open source projects created by [Ian Lunn](https://github.com/IanLunn), please consider making a donation.

Your donation is not-for-profit (or beer!), and will allow Ian to spend a little less time on client projects and more time supporting and creating open source software.

Thank you.

**Bitcoin:**

Bitcoin donations may be sent to the following address:

<div style="text-align: center;">
<a href="bitcoin:1KEbFvcXL8m6LogG2wjSUFz2xH6PeN6jRd?label=Hover.css%20Development"><img src="http://ianlunn.co.uk/images/btc-donate.jpg" /></a>
<p>1KEbFvcXL8m6LogG2wjSUFz2xH6PeN6jRd</p>
</div>
