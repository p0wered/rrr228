<template>
  <div>
    <div class="flexbox-lg">
      <h1 class="web-title">SHOP CARDS VUE</h1>
      <div class="flexbox-sm">
        <ItemCard v-for="product in products" :data="product" :key="product"></ItemCard>
      </div>
    </div>
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
          name: "Long-sleeve Sabbath",
          image: "https://sun1-21.userapi.com/impg/7gYsefOGsO-y117JTbmGS35wctuzcxq48SF6pA/Na4igMugiOM.jpg?size=520x0&quality=95&sign=4d61649ae57519f8ff98a230147e426d",
          count: 0,
          price: 39.99
        },
        {
          name: "Hoodie Flame",
          image: "https://sun1-98.userapi.com/impg/O9PKxUuEvDt810WXyEW0IsRvTT5KLnwEejEWBw/ZuzfODmTIWc.jpg?size=520x0&quality=95&sign=7b22cc706b8cc2c3a1dc78f2f1f1e1ca",
          count: 0,
          price: 69.99
        },
        {
          name: "ADIDAS Old Skool",
          image: "",
          count: 0,
          price: 1000
        }
      ],
    }
  },
}

</script>
