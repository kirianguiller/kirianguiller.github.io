<template>
  <div id="app">
    <Navbar />
    <Home />
  </div>
</template>

<script>
import Home from "./views/Home.vue";
import Navbar from "@/components/Navbar.vue";

export default {
  name: "App",
  components: {
    Home,
    Navbar
  }
};
</script>

<style>
*,
*::before,
*::after {
  box-sizing: border-box;
  text-align: center;
  margin: 0px;
  padding: 0px;
}

/* :root {
  --main-txt-color : #39b982;

  it doesn't load in other .vue
} */

html {
  -webkit-text-size-adjust: 100%;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  scroll-behavior: smooth;
}

/* define website variables */
html {
  --color-main: #39b982;
  --color-dark: #33363c;
  --color-dark-accent: #7d7a67;
  --color-light: #fafffd;
  --color-light-accent: #86babf;
  --font-main: 'Lato', sans-serif, "Roboto", "Noto Sans CJK SC", "Open Sans", sans-serif;
  --font-cursive: "Comic Neue", cursive;
  --font-headline: "Satisfy", cursive;
}

body {
  font-family: var(--font-main);
  font-size: 20px;
  font-size: min(max(16px, 4vw), 22px);
  line-height: 1.5;
}

.cursive-font {
  font-family: var(--font-cursive);
}

/* hr {
  box-sizing: content-box;
  height: 0;
  overflow: visible;
} */
a {
  color: var(--color-main);
  font-weight: 600;
  background-color: transparent;
}
img {
  border-style: none;
  width: 100%;
}
h1,
h2,
h3,
h4,
h5,
h6 {
  /* display: flex; */
  align-items: center;
  font-family: var(--font-cursive);
}
h1 {
  font-size: 2.5em;
  font-weight: 700;
}
h2 {
  font-size: 1.8em;
  font-weight: 700;
}
h3 {
  font-size: 1.6em;
  font-weight: 700;
}
h4 {
  font-size: 1.4em;
  font-weight: 700;
}
h5 {
  font-size: 1.2em;
  font-weight: 700;
}
h6 {
  font-size: 1.1em;
  font-weight: 700;
}

.fixed-header {
  position: fixed;
  left: 0px;
  top: 0px;
  width: 100%;
  height: 60px;
  z-index: 100;
  background-color: var(--color-main);
  box-shadow: 0 1px 6px 0 rgba(32, 33, 36, 0.28);
}

/* 
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
} */

.main {
  color: var(--color-main);
}

.bg-main {
  background-color: var(--color-main);
}

.dark {
  color: var(--color-dark);
}

.bg-dark {
  background-color: var(--color-dark);
}

.dark-accent {
  color: var(--color-dark-accent);
}

.bg-dark-accent {
  background-color: var(--color-dark-accent);
}

.light {
  /* color: #f5eff4; */
  color: var(--color-light);
}

.bg-light {
  /* background-color: #f5eff4; */
  background-color: var(--color-light);
}

.light-accent {
  color: var(--color-light-accent);
}
</style>
