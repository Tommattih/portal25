### Build

#### db objects (thinking):

- aside-image [{}{}{}]\* props using db?

- new-post {[]}
  - {h3 /title}, \*?
  - {h4 /subject},
  - {img, imgsource, alt, figcaption},
  - {paragraphs /[]}

#### props para darkmode? (nope)

- [x] isDark é uma prop em Navbar.vue, boolean
- [x] isDark recebe false em App.vue
- [x] Trazer botão de .lightMode para App.vue e no methods usar um if/else pra alterar a classe dinamicamente

~~O método que troca fica em navbar ou em app?~~

~~Em App.vue vai uma função que observa isDark e adiciona ou remove classe usando getElement/querySelector, ou~~

~~Em App.vue vai um v-if/v-else que observa isDark e usa a div#app com a classe correspondente, ou~~

#### New content

components forms:

- [_] environment
- [_] services
- [_] faq

- [_] submit event to json-server data

### Styles

#### Colors to var (light set)

// --bg-color: #606639;
// --font-color2: #262b05;

---

:root {
// bg navbar/h1/h2/h3
--bg-titles: #83895d;

// text navbar, h1, h2, h3
--txt-titles: #f3f7e0;

// bg h4, asideBox
// --bg-subject: #b1c68b33;
--bg-subject: #8886;

--select-route: #00000066;

--bg-body-base: #a6ac7f;
--bg-body: linear-gradient(
90deg,
#a6ac7fcc 0%,
#f0f0e1 1%,
#f4f7e399 99%,
#a6ac7fcc 100%
);
--bg-main-content: #fff;

--bg-hover2: #9daf7145; //testar
--bg-hover: #dde3bdaa;
--txt-hover: #324028;

--txt-color: #1d2618;
// --txt-color: #2c3e50;

//borders
--border-double: ;
--border-dashed: 2px dashed rgb(60 60 40 / 15%);
--border-glass: 2px solid rgba(255, 255, 255, 0.75);

//shadows
--shadow-button: -1px 2px 5px #2d3d2585; //using
--shadow-mobile: 0 1px 5px #2d3d2585;
--shadow-main: -2px 2px 10px rgb(0 0 0 / 50%);
}

#### Colors to var (dark set)

--bg-titles: #1D2618; //no change?
--txt-titles: ##f3f7e0; //+ bg body?

--bg-hover: #4e7367cc
--bg-main-content: #000;
--bg-body: gradient; linear-gradient(90deg, # 0%, #) 1%, # 99%, # 100%);
--shaddow-button: -1px 1px 5px #2d3d2585; /using
--main-shadow: -2px 2px 10px rgb(0 0 0 / 50%);

#### SEO

invert h4 with h5 (and h5 to h4)

- [x] aside
- [_] main

set width for all images

- [_] ...

set alt for all images

- [_] ...

change svg to png compressed

- [_] ...

create png (compressed)

- [_] base link
- [_] docs link

/ use
nav a a:hover {
color: ##324028;
background: #dde3bdaa;
border: 1px double var(--bg-color);
border-radius: 0.75rem;
padding: 0.5em;
}
