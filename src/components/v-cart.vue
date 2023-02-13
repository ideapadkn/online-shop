<template>
  <div class="v-cart">
    <h1>Cart</h1>
    <v-cart-item 
      v-for="(item, index) in cartData"
      :key="item.article"
      :cartItemData="item"
      @deleteFromCart="deleteFromCart(index)"
    />
  </div>
</template>

<script>
import vCartItem from './v-cart-item.vue';
import { mapActions } from 'vuex';
  export default {
    name: 'v-cart',
    components: {
      vCartItem
    },
    props: {
      cartData: {
        type: Array,
        default() {
          return []
        }
      }
    },
    data() {
      return {

      }
    },
    methods: {
      ...mapActions([
        'DELETE_FROM_CART'
      ]),
      deleteFromCart(index) {
        this.DELETE_FROM_CART(index)
      }
    }
  }
</script>

<style>

</style>