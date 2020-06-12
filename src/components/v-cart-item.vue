<template>
  <div class="v-cart-item">
    <img class="v-cart-item__image" :src=" require('../assets/images/' + cart_item_data.image)" alt="">
    <div class="v-cart-item__info">
      <p>{{cart_item_data.name}}</p>
      <p>{{cart_item_data.price}}</p>
      <p>{{cart_item_data.article}}</p>
    </div>
    <div class="v-cart-item__quantity">

      <p>Qry:</p>
      <span>
        <span 
        class="click" 
        @click="decrementItem"
        >-</span>
          {{cart_item_data.quantity}} 
      </span>
       <span 
       class="click" 
       @click="incrementItem"
       >+</span>
       </div>
    <button @click="deteteFromCart">Delete</button>
  </div>
</template>

<script>

export default {
 name: 'v-cart-item',
 props:{
   cart_item_data:{
     type: Object,
     default(){
       return {}
     }
   }
 },
 data(){
	return{}
 },
  mounted(){
	
 },
 methods:{

   deteteFromCart(){
     this.$emit('deteteFromCart')
   },
   decrementItem(){
     this.$emit('decrement')
   },
   incrementItem(){
     this.$emit('increment')
   }
 }

}
</script>


<style lang="scss">
	.v-cart-item{
    display: flex;
    justify-content: space-between;
    align-items: center;
    flex-wrap: nowrap;
		box-shadow: 0 0 8px 0 #e0e0e0;
		padding: $padding*2;
		margin-bottom: $margin*2;
    
  }
  .v-cart-item__image{
      width: 100px;
  }
  .click{
    cursor: pointer;
  }
</style>
