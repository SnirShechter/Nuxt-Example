<template>
  <nuxt-link :to="'/products/'+product.id" class="app-product">
    <div class="image" :style="{ backgroundImage: `url(${product.image.url})` }"/>
    <div class="title">
      {{product.title}}
    </div>
    <div class="price">
      {{product.price}}
    </div>
  </nuxt-link>
</template>

<script>
  export default {
    name: 'app-product',
    props: {
      product: {
        type: Object,
        default: () => {
          return {
            link: '/',
            image: '',
            title: 'Product title',
            price: 'Product price',
          }
        }
      }
    }
  }
</script>

<style lang="scss" scoped>
  .app-product {
    .image {
      background-color: black;
      height: 280px;
      margin-bottom: 17px;
      background-size: cover;
      background-position: center;
    }
    .title {
      font-size: 18px;
      font-weight: bold;
      margin-bottom: 15px;
    }
  }
</style>
