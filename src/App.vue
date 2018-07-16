<template>
  <div id="app">
    <SiteHeader/>
    <router-view/>
  </div>
</template>

<script>
import SiteHeader from './components/SiteHeader';

export default {
  components: {
    SiteHeader,
  },
  name: 'App',
};
</script>

<style>
*,
*::before,
*::after {
  box-sizing: border-box;
}

html {
  font: normal 1em/1.5 Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

body {
  font-size: .75rem;
  line-height: 1.5;
  margin: 0;
  padding: 0;
  color: #444;
  background-color: #fff;
}

nav ul {
  margin: 0;
  padding: 0;
  list-style-type: none;
}

nav li {
  padding: 0;
}

a {
  color: #0087cf;
  text-decoration: none;
}

a:focus,
a:hover {
  text-decoration: underline;
  outline: none;
}

abbr {
  text-decoration: none;
}
</style>
