<template>
  <button :class="{ full: fullBg }">{{ content }}</button>
</template>

<script>
  export default {
    name: 'Btn',
    props: ['fullBg', 'content'],
  };
</script>

<style lang="scss" scoped>
  @import '@/scss/var';
  button {
    @import '@/scss/var';
    background-color: transparent;
    color: $white;
    padding: 10px;
    border: 2px solid $brand;
    transition: background-color 0.4s;
    cursor: pointer;
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
      transform: rotate(3deg);
    }
    40% {
      transform: rotate(-3deg);
    }
    60% {
      transform: rotate(3deg);
    }
    80% {
      transform: rotate(-3deg);
    }
    100% {
      transform: rotate(0deg);
    }
  }
</style>
