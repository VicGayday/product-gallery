<template>
  <div id="app">
    <Header/>
    <Slider :slides = "slide"/>
    <Products :products="fetchedProducts" />
  </div>
</template>

<script>
import axios from "axios"
import Header from './components/Header.vue'
import Slider from './components/Slider.vue'
import Products from './components/Products.vue'
export default {
  name: 'App',
  components: {
    Header, Slider, Products,
  },
  data() {
    return {
     fetchedProducts: [],
     slide: ""
    }
  },
  methods: {
    async fetchProducts() {
      try {
        const response = await axios.get("https://dummyjson.com/products?limit=100")
        this.fetchedProducts = response.data.products;
        localStorage.setItem('products', JSON.stringify(response.data.products))
      } catch (err) {
        console.log(err);
      }
    },
    async fetchSlides() {
      try {
        const response = await axios.get("https://random.dog/woof.json")
        this.slide = response.data.url
        console.log(this.slide);
      } catch (err) {
      console.log(err);
    }
    }
  },
  async mounted() {
    const savedProducts = JSON.parse(localStorage.getItem('products'))
    !savedProducts ?
   await this.fetchProducts() : this.fetchedProducts = savedProducts;
   await this.fetchSlides()
  }
}
</script>

<style scoped>
</style>
