<template>
  <div class="v-main-wrapper">
    <v-catalog />
    <v-cart
      v-if="CART.length"
      :cartData="CART"
    />
  </div>
</template>

<script>
import vCatalog from '@/components/v-catalog.vue';
import vCart from '@/components/v-cart.vue';
import { mapGetters } from 'vuex';

  export default {
    name: 'v-main-wrapper',
    components: {
      vCatalog, vCart
    },
    props: {},
    data() {
      return {
        title: ''
      }
    },
    computed: {
      ...mapGetters([
        'CART'
      ])
    },
    methods: {},
    watch: {},
    mounted() {
      // console.log('Hello i am alive')
    }
  }
</script>

<style lang="scss">
.v-main-wrapper {
  max-width: 900px;
  margin: 0 auto;
}
</style>