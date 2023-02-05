<template>
  <div class="header-container">
    <div class="logo-wrapper">
      <img :src="iconContent" alt="logo" class="logo-img">
    </div>
    <button class="update-btn">Update products</button>
  </div>
</template>
<script>
import { defineComponent } from 'vue'
import logo from "@/assets/logo.svg"

export default defineComponent({
  name: "Header",
  setup() {
    const iconContent = logo
   return {
iconContent
   }
  },
})
</script>

<style scoped>
.header-container {
  background-color: #5775A9;
  display: flex;
  justify-content: space-between;
  align-items: center;
  height: 48px;
}
.update-btn {
  border-radius: 100px;
  border: none;
  padding: 8px 16px;
  background-color: #FFFFFF;
  margin-right: 5%;
  /* width: 15%;
  height: 15%; */
}

.logo-img {
  width: 70%;
  height: 70%;
}

.logo-wrapper {
  margin-left: 5%;
}
</style>
