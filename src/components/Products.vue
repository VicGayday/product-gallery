<template>
<div class="products-wrapper">
  <div v-for="product in products" :key="product.id" class="product-card">
    <img :src="product.thumbnail" alt="product picture">
    <p><span>Brand:</span> {{ product.brand }}</p>
    <p><span>Category:</span>{{ product.category }}</p>
    <p><span>Description:</span>{{ product.description }}</p>
    <p><span>In stock:</span>{{ startTimer(product.stock) }}</p>
  </div>
  </div>
</template>

<script>
export default {
  name: 'Products',
  props: {
    products: {
      type: Array,
      required: true,
    }
  },
  data() {
    return {
     timer: null,
     currentTime: 60
    }
  },
  methods: {
    startTimer(prod) {
  this.timer = setInterval(() => {
    prod >=0 ? prod-- : this.stopTimer()
  }, 1000);
    },
  stopTimer() {
    clearTimeout(this.timer)
  }
  },
  mounted() {
    this.startTimer()
  },
  destroyed() {
    this.stopTimer()
  }
}
</script>
<style scoped>
  .products-wrapper {
    width: 100%;
    display: flex;
    justify-content: flex-start;
    flex-wrap: wrap;
  }
  .product-card {
    width: 25%;
    height: 20%;
  }
  img {
    height: 70%;
    width: 80%;
  }
  span {
    font-weight: bold;
  };
  p {
   margin: 0px;
  }

</style>