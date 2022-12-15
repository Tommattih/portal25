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

:root {
// --bg-color: #606639;
// --font-color2: #262b05;

// bg navbar/h1/h2/h3
--bg-titles: #83895d;
// --bg-titles: #606639;

// text navbar, h1, h2, h3
--txt-titles: #f3f7e0;

// bg h4, asideBox
--bg-subject: #b1c68b33;
--border-sub: #8886;

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
--border-double: 2px double #edfbff75;
--border-dashed: 2px dashed var(--bg-hover2);
--border-glass: 2px solid rgba(255, 255, 255, 0.75);

//shadows
--shadow-button: -1px 2px 5px #2d3d2585; //using
--shadow-mobile: 0px 1px 3px #0204;
--shadow-main: -2px 2px 10px rgb(0 0 0 / 50%);
}

#### Colors to var (dark set)

.dark {
// bg navbar/h1/h2/h3
//--bg-titles: #343819;
--bg-titles: #00447c;

// text navbar, h1, h2, h3
--txt-titles: #bbd1e4;

// bg h4, asideBox
--bg-subject: #335c4f5c;
--border-sub: #8886;

--select-route: #00000066;

--bg-body-base: #0e2038da;
--bg-body: linear-gradient(
90deg,
#000 0%,
#06152cea 1%,
#0e2038da 99%,
#000 100%
);
--bg-main-content: #06152cea;

--bg-hover2: #0f505475; //testar
--bg-hover: #54b5d621;
--txt-hover: #bef2ff;

// --txt-color: #2c3e50;
--txt-color: #bbd1e4;

//borders
--border-double: 1px double rgba(107, 203, 226, 0.457);
--border-dashed: 2px dashed var(--bg-hover);
--border-glass: 2px solid #1a588168;

//shadows
--shadow-button: -1px 2px 5px #264a5085; //using
--shadow-mobile: 0px 1px 3px rgba(0, 0, 0, 0.753);
--shadow-main: -2px 2px 10px rgb(0 0 0 / 50%);
}

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

--bg-color: #343819;
--font-color1: #bbd1e4;
--font-color2: #00447c;
--font-nav-active: rgb(89, 247, 255);
--bg-section-color: #1e1e1e;
--bg-base-color: #ff00fb;
--bg-base-color1: #000;
--bg-base-color2: #06152cea;
--bg-base-color3: #0e2038da;
--bg-section-color: #1e1e1e;
--bg-base-color: #ff00fb;
--bg-base-color1: #000;
--bg-base-color2: #06152cea;
--bg-base-color3: #0e2038da;
}

background: linear-gradient(
90deg,
var(--bg-base-color1) 0%,000
var(--bg-base-color2) 1%,06152cea
var(--bg-base-color3) 99%,0e2038da
var(--bg-base-color1) 100% 000
);
--bg-section-color: #f3f2ed;
--bg-base-color: #a6ac7f;
--bg-base-color1: #a6ac7fcc;
--bg-base-color2: #f0f0e1;
--bg-base-color3: #f4f7e399;
