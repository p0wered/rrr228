<template>
  <div>
    <div class="shop-card" :style="{'background-image': 'url('+ data.image +')'}">
      <div class="card-inner">
        <div class="card-name">
          {{data.name}}
        </div>
        <div class="card-price">
          {{data.price}}$
        </div>
        <div v-if="data.count > 0" class="btn-box">
          <button class="btn-main" @click="addItem(data, 'remove')"> - </button>
          <p style="margin: 1rem">{{data.count}}</p>
          <button class="btn-main" @click="addItem(data, 'add')"> + </button>
        </div>
        <div v-else>
          <button @click="addItem(data, 'add')" class="cart-btn">Add To Cart</button>
        </div>
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
    addItem(data, type) {
      console.log('я сработал')
      if(type === 'add'){
        data.count++
      }
      else{
        data.count--
      }
    },
    clearCard()
    {
      localStorage.setItem('card','');
      localStorage.clear()
    }
  }
}
</script>
