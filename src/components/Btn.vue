<template>
  <button>SIGN UP NOW!</button>
</template>

<script>
  export default {
    name: 'Btn',
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
</style>
