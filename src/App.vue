<template>
  <div>
    <div><NavbarComponent /></div>
    <div id="home"><HeaderComponent /></div>
    <div id="main"><OrderComponent /></div>
    <div id="aboutUs"><AboutUsComponent /></div>
  </div>
</template>

<script>
import HeaderComponent from './components/Header.vue'
import NavbarComponent from './components/Navbar.vue'
import OrderComponent from './components/OrderPage.vue'
import AboutUsComponent from './components/AboutUs.vue'

export default {
  name: 'App',
  components: {NavbarComponent, HeaderComponent, OrderComponent, AboutUsComponent}
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

#main {
  margin-top: 25em;
}
</style>
