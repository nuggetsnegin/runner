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
    Product
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
</style>
