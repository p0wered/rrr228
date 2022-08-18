<template>
  <div>
    <div class="shop-card" :style="{'background-image': 'url('+ data.image +')'}">
      <div class="card-name">
        {{data.name}}
      </div>
      <div v-if="data.count > 0">
        <button> - </button>
        <p>0</p>
        <button> + </button>
      </div>
      <div v-else>
        <button>Добавить в корзину</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "ItemCard",
  props:['data'],
  data: function () {
    return {
      card: JSON.parse(localStorage.getItem('card')),
    }
  },
  methods: {
    addToCard(product) {
      let a = []
      // eslint-disable-next-line no-unused-vars
      a = JSON.parse(localStorage.getItem('card')) || [];
      a.push(product)
      localStorage.setItem('card', JSON.stringify(a));
      product.count++
    },
    clearCard()
    {
      localStorage.setItem('card','');
      localStorage.clear()
    }
  }
}
</script>

<style scoped>

</style>