<template>
  <div>
    <div><NavbarComponent /></div>
    <div id="home"><HeaderComponent /></div>
    <div id="main"><OrderComponent /></div>
    <div id="aboutUs"><AboutUsComponent /></div>
    <div id="contact"><ContactComponent /></div>
    <div id="footer"><FooterComponent /></div>
  </div>
</template>

<script>
import HeaderComponent from './components/Header.vue';
import NavbarComponent from './components/Navbar.vue';
import OrderComponent from './components/OrderPage.vue';
import AboutUsComponent from './components/AboutUs.vue';
import ContactComponent from './components/Contact.vue';
import FooterComponent from './components/Footer.vue';

export default {
  name: 'App',
  components: {NavbarComponent, HeaderComponent, OrderComponent, AboutUsComponent, ContactComponent, FooterComponent}
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#home, #main {
  padding: 0 0 50em 0;
}
#aboutUs {
  padding: 0 0 30em 0;
}

</style>
