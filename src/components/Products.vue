<template>
  <section class="products">
      <h1>Lista prodotti</h1>

      <div class="container prods-container">
          <Card 
            v-for="(product, index) in products"
            :key="index"
            :single-product="product"
          />
      </div>
  </section>
</template>

<script>
import Card from './Card';
import pastas from '../data/pastas';

export default {
    name: "Products",
    components: {
        Card
    },
    data: function() {
        return {
            products: pastas
        }
    }
}
</script>

<style lang="scss" scoped>
    @import '../style/mixins';

    .products {
        margin: 60px 0;
        padding: 60px 0;
        background: url('../assets/images/bg-prods.jpg');
        text-align: center;
    }

    .products h1 {
        font-size: 36px;
    }

    .prods-container {
        @include center('pippo');
        flex-wrap: wrap;
    }
</style>