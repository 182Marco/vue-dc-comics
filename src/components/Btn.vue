<template>
  <button :class="{ full: fullBg, more: more }">{{ content }}</button>
</template>

<script>
  export default {
    name: 'Btn',
    props: ['fullBg', 'content', 'more'],
  };
</script>

<style lang="scss" scoped>
  @import '@/scss/var';
  @import '@/scss/mixins';
  button {
    @import '@/scss/var';
    background-color: transparent;
    color: $white;
    padding: 10px 15px;
    border: 2px solid $brand;
    transition: background-color 0.4s;
    cursor: pointer;
    font-weight: 700;
    &:hover {
      background-color: $brand;
    }
    &.full {
      background-color: $brand;
    }
    &.full:hover {
      animation: tremble;
      animation-duration: 0.3s;
    }
  }

  @keyframes tremble {
    0% {
      transform: rotate(0deg);
    }
    20% {
      transform: rotate(2deg);
    }
    40% {
      transform: rotate(-2deg);
    }
    60% {
      transform: rotate(2deg);
    }
    80% {
      transform: rotate(-2deg);
    }
    100% {
      transform: rotate(0deg);
    }
  }
</style>
