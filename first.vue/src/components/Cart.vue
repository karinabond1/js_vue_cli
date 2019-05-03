<template>
    <div id="app">
        <h1>Cart!</h1>
        <div class="cart">
      <h3>Cart:</h3>
      <ul>
        <li v-for="(item, key) in ingrArr" v-if="item.count" :key="key" :item="item" style="margin-bottom: 5px">
          <button type="button" @click="remove(item)">-</button>
          <span class="cart__name">{{ item.name }} x {{ item.count }}</span> - 
          <span class="cart__price">{{ item.price*item.count }}</span>
        </li>
      </ul>
      <span class="cart__total">Total: {{ total__price }}</span>
    </div>
    </div>
</template>
<script>
export default {
    data(){
       return{
ingrArr: JSON.parse(localStorage.ingr || '')
       }
   } ,

   
   methods: {    
    remove: function(item) {
      item.count--;
      localStorage.ingr = JSON.stringify(this.ingrArr);
    }
  },
  computed: {
    total__price: function() {
      let total = 0;
      this.ingrArr.forEach((el) => {
        if (el.count) {
          total += el.price * el.count;
        }
      });
      return total;
    },
  },
}
</script>
<style >
    
</style>