<template>
  <button :class="{ full: fullBg }">{{ content }}</button>
</template>

<script>
  export default {
    name: 'Btn',
    props: ['fullBg', 'content'],
  };
</script>

<style scoped>
  button {
    background-color: transparent;
    color: var(--white);
    padding: 10px;
    border: 2px solid var(--brand);
    transition: background-color 0.4s;
    cursor: pointer;
  }
  button:hover {
    background-color: var(--brand);
  }
  button.full {
    background-color: var(--brand);
  }
  button.full:hover {
    animation: tremble;
    animation-duration: 0.3s;
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
