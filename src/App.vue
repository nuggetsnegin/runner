<template>
  <div id="app">
    <Header/>
    <Gallery/>
    <Product/>
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Gallery from './components/Gallery.vue'
import Product from './components/Product.vue'

export default {
  name: 'App',
  components: {
    Header,
    Gallery,
    Product,
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@300;400;500&display=swap');
#app {
  font-family: Roboto, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  max-width: 100vw;
  max-height: 100vh;
}
</style>
