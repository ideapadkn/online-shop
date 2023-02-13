<template>
  <div class="v-catalog-item">
    <img class="img" :src="require('@/assets/images/' + productData.image)" alt="img">
    <p class="v-catalog-item__name">{{ productData.name }}</p>
    <p class="v-catalog-item__price">Price: {{ productData.price }}$</p>
    <button 
      class="v-catalog-item__add_to_cart_btn btn"
      @click="sendDataToParent"
    >
      Add To Card
    </button>
  </div>
</template>

<script>
  export default {
    name: 'v-catalog-item',
    props: {
      productData: {
        type: Object,
        default() {
          return {}
        },
      }
    },
    data() {
      return {

      }
    },
    methods: {
      sendDataToParent() {
        this.$emit('sendArticle', this.productData.article )
      }
    }
  }
</script>

<style lang="scss">
.v-catalog-item {
$padding: 8px;
$margin: 8px;
$radius: 4px;


  flex-basis: 25%;
  box-shadow: 0 5px 8px 0 #e0e0e0;
  padding: $padding*2;
  margin-bottom: $margin*2;
  .img {
    max-width: 250px;
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