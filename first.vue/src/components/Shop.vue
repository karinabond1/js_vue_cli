<template>
  <div id="app">
    <h1>Shop!</h1>
    <div class="catalog">
      <h3>Catalog:</h3>
      <ul>
        <li v-for="(item, key) in ingrArr" :key="key" :item="item" style="margin-bottom: 5px">
          <button type="button" @click="add(item)">+</button>
          <span class="catalog__name">{{ item.name }}</span> -
          <span class="catalog__price">{{ item.price }}</span>
        </li>
      </ul>
    </div>
  </div>
</template>
<script>
//import Products from '@/shop/products'
var ingredients = [
  {
    id: 1,
    name: "milk",
    price: 100,
    count: 0
  },
  {
    id: 2,
    name: "bread",
    price: 200,
    count: 0
  },
  {
    id: 3,
    name: "oil",
    price: 300,
    count: 0
  },
  {
    id: 4,
    name: "apple",
    price: 400,
    count: 0
  },
  {
    id: 5,
    name: "carrot",
    price: 500,
    count: 0
  },
  {
    id: 6,
    name: "banana",
    price: 600,
    count: 0
  },
  {
    id: 65,
    name: "teeeeeest",
    price: 600,
    count: 0
  }
];
export default {
  data() {
    return {
      ingrArr: JSON.parse(localStorage.ingr || JSON.stringify(ingredients))
    };
  },
  methods: {
    add: function(item) {
      item.count++;
      localStorage.ingr = JSON.stringify(this.ingrArr);
    }
  },
  components: {
    // Products
  }
};
</script>
<style >
</style>