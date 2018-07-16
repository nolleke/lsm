<template>
  <header class="site-header">
    <input type="checkbox" id="main-nav-toggle" class="flyout-toggle">
    <h1><label for="main-nav-toggle"><img class="logo" src="https://www.lushstories.com/images/logowords.png" alt="Lush Stories"></label></h1>
    <nav>
      <ul>
        <li v-for="menuItem in menu" :key="menuItem.label">
          <a :href="menuItem.url">{{ menuItem.label }}</a>
        </li>
      </ul>
    </nav>
  </header>
</template>

<script>
const menu = [
  { label: 'Home', url: '/' },
  { label: 'Contact', url: '/contact' },
  { label: 'Join Lush', url: '/join' },
  { label: 'Login', url: '/login' },
];

export default {
  name: 'SiteHeader',
  data() {
    return {
      menu,
    };
  },
};
</script>

<style scoped>
header {
  position: relative;
  z-index: 1;
  color: #fff;
  padding: 36px 0 0;
}

.flyout-toggle {
  position: absolute;
  left: -999em;
}

h1 {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  z-index: 1;
  font-size: 1em;
  margin: 0;
  background-color: #e60022;
}

h1::before {
  content: '';
  position: absolute;
  left: 0;
  right: 0;
  bottom: 36px;
  z-index: 0;
  height: 50em;
  background-color: #e60022;
}

label {
  display: block;
  position: relative;
  padding: 5px 10px 5px 7px;
  cursor: pointer;
}

label::after {
  content: '›';
  position: absolute;
  top: -5px;
  right: 8px;
  display: inline-block;
  font-size: 2rem;
  font-weight: normal;
  transform: rotate(90deg);
}

.flyout-toggle:checked ~ h1 label::after {
  right: 12px;
  transform: rotate(-90deg);
}

img {
  display: block;
}

nav {
  position: fixed;
  top: 36px;
  left: 0;
  right: 0;
  overflow: hidden;
  font-size: 1rem;
  background-color: #e60022;
  transform: translateY(-120%);
  transition: transform .125s ease;
}

.flyout-toggle:checked ~ nav {
  transform: translateY(0);
}

ul {
  padding: 5px 0 10px;
  -webkit-column-count: 2;
  column-count: 2;
  column-fill: balance;
  -webkit-column-gap: 0;
  column-gap: 0;
}

a {
  display: block;
  color: #fff;
  text-decoration: none;
  padding: 5px 10px;
}

a:focus,
a:hover {
  background-color: #444;
}
</style>
