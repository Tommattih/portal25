<template>
  <div id="app" :class="colorMode">
    <NavBar />
    <!-- to toggle theme -->
    <div class="lightButton">
      <transition name="appear">
        <img
          v-if="isDark"
          @click="changeColor()"
          src="img/navItens/button-moon.png"
          alt="icon-moon"
          height="40"
        />
      </transition>
      <transition name="appear">
        <img
          v-if="!isDark"
          @click="changeColor()"
          src="img/navItens/button-sun.png"
          alt="icon-sun"
          height="40"
        />
      </transition>
    </div>
    <PortalHeader numberArea="25" nameArea="Parque Vitória do Sol Nascente" />
    <div>
      <router-view class="content" />
    </div>
    <footer class="mt-2">
      <p @click="clicou()" class="mb-0 pb-2">M.T. Lins - Brasil - 2022</p>
    </footer>
  </div>
</template>

<script>
// @ is an alias to /src
import NavBar from '@/components/header/NavBar.vue'
import PortalHeader from '@/components/header/PortalHeader.vue'
export default {
  name: 'HomeView',
  components: {
    PortalHeader,
    NavBar
  },
  data() {
    return {
      isDark: false,
      colorMode: ''
    }
  },
  methods: {
    changeColor() {
      this.isDark = !this.isDark
      if (this.isDark) {
        return (this.colorMode = 'dark')
      } else {
        return (this.colorMode = '')
      }
    }
  }
}
</script>

<style lang="scss">
* {
  box-sizing: border-box;
  list-style: none;
  margin: 0;
  padding: 0;
}

:root {
  // --bg-color: #606639;

  // bg navbar/h1/h2/h3
  --bg-titles: #83895d;
  //   --bg-titles: #606639;

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

.dark {
  // bg navbar/h1/h2/h3
  --bg-titles: #032e42;

  // text navbar, h1, h2, h3
  --txt-titles: #bbd1e4;

  // bg h4, asideBox
  --bg-subject: #335c4f5c;
  --border-sub: #8886;

  --select-route: #064c85;

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

::-webkit-scrollbar {
  width: 0.75rem;
}
::-webkit-scrollbar-track {
  background: var(--bg-main-content);
}
::-webkit-scrollbar-thumb {
  background: var(--bg-titles);
}
::-webkit-scrollbar-thumb:hover {
  background: var(--bg-body-base);
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: var(--txt-color);
  overflow-x: hidden;
  max-width: 100vw;
  min-height: 100vh;
  background: var(--bg-body-base);
  background: var(--bg-body);
}

//ColorMode button
.lightButton img {
  cursor: pointer;
  position: fixed;
  z-index: 10;
  top: 0;
  right: 0.5rem;
  margin: 0.2rem;
}
//animation
.appear-enter-active,
.appear-leave-active {
  transition: transform 0.3s, opacity 0.5s;
}
.appear-leave-to,
.appear-enter {
  transform: scale(0);
  opacity: 0;
}
.appear-leave,
.appear-enter-to {
  transform: scale(1);
  opacity: 1;
}

h1,
h2,
h3 {
  color: var(--txt-titles);
  background-color: var(--bg-titles);
}

h3,
h4 {
  box-shadow: var(--shadow-mobile);
  border-radius: 0.25rem;
}

h4 {
  background-color: var(--bg-subject);
  font-size: 0.25rem; /* nao pega pq?*/
}
h1,
.bg-color,
.header,
.boxContent {
  box-shadow: var(--shadow-button);
}

nav {
  a {
    text-decoration: none;
    font-weight: bold;
    color: var(--txt-titles);
    transition: 0.4s;

    &.router-link-exact-active {
      color: var(--select-route);
      background: none;
    }
    a:hover {
      background: var(--bg-hover);
      color: var(--txt-hover);
      border: var(--border-double);
      border-radius: 0.75rem;
      padding: 0.5em;
    }
  }
}

.content {
  width: 100%;
  display: inline-flex;
  flex-direction: row;
  align-items: flex-start;
  justify-content: flex-end;
  gap: 0.5rem;
  padding: 0.5rem 1rem;
}
.boxContent {
  width: 100%;
  background: var(--bg-main-content);
  border: var(--border-dashed);
  display: flex;
  flex-direction: column;
  margin-bottom: 0.5rem;
  padding: 0 0.25rem;
}
.boxContent p {
  padding: 0.25rem;
}

@media only screen and (max-width: 768px) {
  .content {
    gap: 0.25rem;
    margin: 0;
    padding: 0.5rem;
    align-items: flex-start;
  }
  .asideBox {
    box-shadow: var(--shadow-mobile);
    //testar
  }
}
</style>
