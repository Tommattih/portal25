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
:root {
  --bg-color: #606639;
  --font-color2: #262b05;
  --font-color: #f3f7e0;
  box-sizing: border-box;
  list-style: none;
  margin: 0;
  padding: 0;
}
::-webkit-scrollbar {
  width: 0.5rem;
}
::-webkit-scrollbar-track {
  background: var(--font-color);
}
::-webkit-scrollbar-thumb {
  background: var(--bg-color);
}
::-webkit-scrollbar-thumb:hover {
  background: var(--font-color2);
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  overflow-x: hidden;
  max-width: 100vw;
  min-height: 100vh;
  background: rgb(166, 172, 127);
  background: linear-gradient(
    90deg,
    rgba(166, 172, 127, 0.8) 0%,
    rgba(240, 240, 225, 1) 1%,
    rgba(244, 247, 227, 0.6) 99%,
    rgba(166, 172, 127, 0.8) 100%
  );
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
  // border: 2px dotted #60663962;
  border: 2px dashed rgb(60 60 40 / 15%);
  display: flex;
  flex-direction: column;
  background: #fff;
}
h3 {
  background-color: var(--bg-color);
  color: var(--font-color);
  box-shadow: 1px 2px 2px #344322;
}
nav {
  a {
    text-decoration: none;
    font-weight: bold;
    color: var(--font-color);
    transition: 0.3s;

    &.router-link-exact-active {
      color: rgba(0, 40, 0, 0.5);
      background: none;
    }
    a:hover {
      color: var(--font-color1);
      background: var(--font-color);
      border: 2px dashed var(--bg-color);
      border-radius: 25%;
      padding: 0.5em;
    }
  }
}
h1,
.bg-color,
.header,
.boxContent {
  box-shadow: -1px 2px 4px rgba(45, 61, 37, 0.52);
}

@media only screen and (max-width: 768px) {
  .content {
    gap: 0.25rem;
    margin: 0;
    padding: 0.5rem;
    align-items: flex-start;
  }
}
</style>
