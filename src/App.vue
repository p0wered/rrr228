<template>
  <div>
    <h1 class="web-title">SHOP CARDS VUE</h1>
    <ItemCard v-for="product in products" :data="product" :key="product"></ItemCard>
  </div>
</template>

<script>
import ItemCard from "@/components/ItemCard";

export default {
  name: 'App',
  components: {
    ItemCard
  },
  data: function () {
    return {
      products: [
        {
          name: "NMD R2 Classic",
          image: "https://sneakers123.s3.amazonaws.com/release/28027/adidas-nmd-r2-cq2400.jpg",
          desc: "lorem lorem lorem VANS TOP ",
          count: 0,
          price: 139.99
        },
        {
          name: "Nike Old Skool",
          image: "",
          desc: "lorem lorem lorem NIKE TOP ",
          count: 0,
          price: 1000
        },
        {
          name: "ADIDAS Old Skool",
          image: "",
          desc: "lorem lorem lorem ADIDAS TOP ",
          count: 0,
          price: 1000
        }
      ],
    }
  },
}

</script>

<style>
#app {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
}
</style>
