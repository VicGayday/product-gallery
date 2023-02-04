<template>
  <div class="header-container">
    <div>
       <img src="@/assets/logo.png" alt="logo" />
    </div>
    <button>Update products</button>
  </div>
</template>
<script>
import { defineComponent } from 'vue'
import logo from "@/assets/logo.svg"

export default defineComponent({
  name: "Header",
  setup() {
  //  const iconContent = logo;
  //  const iconAlt = "logo";
  //  const iconStyle = "width: 10%; height: 10%;";

   return {
    // iconContent,
    // iconStyle,
    // iconAlt,
   }
  },
})
</script>
