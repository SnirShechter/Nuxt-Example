<template>
  <section class="page-product">
    <div
      class="image"
      :style="{ backgroundImage: `url(${product.image.url})` }"
    ></div>
    <div class="content">
      <div class="title">{{ product.title }}</div>
      <div class="price">{{ product.price }}</div>
      <div class="description">{{ product.description }}</div>
      <div class="button">
        Add to cart
      </div>
    </div>
  </section>
</template>

<script>
export default {
  async asyncData({ store, error, params }) {
    try {
      return { product: await store.dispatch("getProductById", params.id) };
    } catch (e) {
      error({ statusCode: 404, message: "Product not found" });
    }
  }
};
</script>

<style lang="scss" scoped>
.page-product {
  display: flex;
  .image {
    background-color: gainsboro;
    width: 50%;
    height: 500px;
    margin-right: 35px;
    background-repeat: no-repeat;
    background-size: contain;
    background-position: center center;
  }
  .content {
    width: 50%;
  }
  .title {
    font-size: 28px;
    font-weight: bold;
    margin-bottom: 15px;
  }
  .price {
    font-size: 18px;
    margin-bottom: 30px;
  }
  .description {
    font-size: 15px;
    margin-bottom: 20px;
  }
  .button {
    transition: transform 0.3s ease;
    color: white;
    background-image: linear-gradient(to top, #31a893, #34ceb3);
    padding: 13px;
    width: 100%;
    max-width: 290px;
    text-align: center;
    font-weight: bold;
    font-size: 18px;
    cursor: pointer;
  }
}
</style>
