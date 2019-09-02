<template>
  <header class="app-header">
    <div class="inner container">
      <div to="/" class="title">
        SPECTRUM
      </div>
      <div class="divider"></div>
      <nav class="nav">
        <nuxt-link to="/">HOME</nuxt-link>
        <nuxt-link to="/products">PRODUCTS</nuxt-link>
      </nav>
    </div>
  </header>
</template>

<script>
  export default {
    name: 'app-header',

  }
</script>

<style lang="scss" scoped>
  @import "../style/config/index";

  .app-header {
    $size: 26px;
    padding-top: $size;
    padding-bottom: $size;
    text-align: center;
    background-color: #f7fcfb;
    font-weight: 300;

    $gap: 15px;
    .title {
      margin-bottom: $gap;
      line-height: 0.85;
      font-size: 40px;
        color: $color-green;
    }

    .divider {
      width: 100%;
      height: 1px;
      background-color: #d7d7d7;
      margin-bottom: $gap;
    }

    .nav {
      display: flex;
      justify-content: center;
      & > * {
        &:not(:last-child) {
          margin-right: 28px;
        }
      }
    }
  }
</style>
