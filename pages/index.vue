<template>
  <div class="app">
    <main>
      <div>
        <input type="text" />
      </div>
      <ul>
        <li class="item flex" v-for="product in products" :key="product.id" @click="moveToDetailPage(product.id)">
          <img class="product-image" :src="product.imageUrl" :alt="product.name">
          <p>{{product.name}}</p>
          <span>{{product.price}}</span>
        </li>
      </ul>
    </main>
  </div>
</template>
  
<script>
import axios from 'axios';

export default {
  async asyncData(){
    const response = await axios.get('http://localhost:3000/products')
    console.log(response)
    const products = response.data.map((item)=>({
      ...item,
      imageUrl:`${item.imageUrl}?random=${Math.random()}`
    }))
    return { products }
  },
  data() {
    return {
      products: []
    }
  },
  methods: {
    moveToDetailPage(id) {
      console.log(id)
    }
  }
  
  // async created() {
    
  // }
}
</script>
<style scoped>
.flex {
  display: flex;
  justify-content: center;
}
.item {
  display: inline-block;
  width: 400px;
  height: 300px;
  text-align: center;
  margin: 0 0.5rem;
  cursor: pointer;
}
.product-image {
  width: 400px;
  height: 250px;
}
.app {
  position: relative;
}
.cart-wrapper {
  position: sticky;
  float: right;
  bottom: 50px;
  right: 50px;
}
.cart-wrapper .btn {
  display: inline-block;
  height: 40px;
  font-size: 1rem;
  font-weight: 500;
}
</style>
  