<template>
  <div class="page-home">
    <div class="title">
      Welcome to Spectrum
    </div>
    <div class="description">({{ runtime }})</div>
  </div>
</template>

<script>
export default {
  asyncData() {
    return {
      runtime: process.server ? "server" : "client"
    };
  }
};
</script>

<style lang="scss" scoped>
.page-home {
  flex-grow: 1;
  display: flex;
  flex-direction: column;
  justify-content: center;
  .title {
    text-align: center;
    font-size: 75px;
  }
  .description {
    font-size: 50px;
    text-align: center;
    color: darkgray;
  }
}
</style>
