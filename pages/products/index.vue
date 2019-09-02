<template>
  <section class="page-products">
    <div class="inner">
      <AppProduct
        v-for="product in products"
        :key="product.id"
        :product="product"
      ></AppProduct>
    </div>
  </section>
</template>

<script>
import AppProduct from "../../components/AppProduct";
export default {
  components: { AppProduct },
  async asyncData({ app, store }) {
    let products = await store.dispatch("getAllProducts");

    return {
      products
    };
  }
};
</script>

<style lang="scss" scoped>
.page-products {
  $gap: 20px;
  .inner {
    display: flex;
    justify-content: center;
    flex-wrap: wrap;
    margin-left: -$gap;
    margin-right: -$gap;
  }
  .app-product {
    width: 100%;
    max-width: 280px;
    margin-left: $gap;
    margin-right: $gap;
    margin-bottom: $gap * 2;
  }
}
</style>
