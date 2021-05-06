<template>
  <a class="box">
    <div class="line"></div>
    <div class="line"></div>
    <div class="line"></div>
  </a>
</template>

<script>
  import navLinks from '@/data/navLinks.js';

  export default {
    name: 'Hamburger',
    data() {
      return {
        navLinks: navLinks,
      };
    },
  };
</script>

<style lang="scss" scoped>
  @import '@/scss/mixins';
  @import '@/scss/var';
  .box {
    width: 27px;
    height: 23px;
    cursor: pointer;
    &:hover .line {
      background-color: $brand;
    }
    .line {
      background-color: $black;
      transition: background-color 0.5s;
      @include width-height(100%, 5px);
    }
  }
</style>
