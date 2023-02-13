<template>
  <div class="v-catalog">
    <h1>Catalog Manga</h1>
    <div class="v-catalog__list">
      <v-catalog-item 
        v-for="product in PRODUCTS"
        :key="product.article"
        :productData="product"
        @sendArticle="showChildArticleinConsole"
      />
    </div>
  </div>
</template>

<script>
import vCatalogItem from '@/components/v-catalog-item.vue';
import { mapActions, mapGetters } from 'vuex';

  export default {
    name: 'v-catalog',
    components: {
      vCatalogItem
    },
    props: {},
    data() {
      return {
        
      }
    },
    computed: {
      ...mapGetters([
        'PRODUCTS'
      ])
    },
    methods: {
      ...mapActions([
        'GET_PRODUCTS_FROM_API'
      ]),
      showChildArticleinConsole(data) {
        console.log(data)
      }
    },
    mounted() {
      this.GET_PRODUCTS_FROM_API()
      .then((response) => {
        if (response.data) {
          console.log('Data arrived')
        }
      })
    }
  }
</script>

<style lang="scss">
.v-catalog {
  &__list {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
    align-items: center;
  }
}
</style>