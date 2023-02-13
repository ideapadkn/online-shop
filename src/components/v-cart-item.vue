<template>
  <div class="v-cart-item">
    <img class="img" :src="require('@/assets/images/' + cartItemData.image)" alt="img">
    <div class="v-cart-item__info">
      <p>{{ cartItemData.name }}</p>
      <p>{{ cartItemData.price }}</p>
      <p>{{ cartItemData.article }}</p>
    </div>
    <div class="v-cart-item-quantity">
      <p>Quantity:</p>
      {{ cartItemData.quantity }}
    </div>
    <button 
      class="btn"
      @click="deleteFromCart"
    >
      Delete
    </button>
  </div>
</template>

<script>
  export default {
    name: 'v-cart-item',
    props: {
      cartItemData: {
        type: Object,
        default() {
          return {}
        }
      }
    },
    data() {
      return {

      }
    },
    methods: {
      deleteFromCart() {
        this.$emit('deleteFromCart')
      }
    },
    mounted() {
      // this.$set(this.cartItemData, 'quantity', 1)
    }
  }
</script>

<style lang="scss">
.v-cart-item {
  display: flex;
  flex-wrap: nowrap;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 15px;
  box-shadow: 0 5px 8px 0 #e0e0e0;
  padding: 16px;
  .img {
    max-width: 250px;
    transition: all .5s;
    filter: grayscale(60%); 
    &:hover {
      scale: 1.05;
      filter: grayscale(0%);
    }
  }
  .btn {
    padding: 10px;
    background-color: transparent;
    border: 1px solid #ccc;
    cursor: pointer;
    transition: all .5s;
    &:hover {
      background-color: #ccc;
    }
  }
}
</style>