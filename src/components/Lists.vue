<template>
  <div>
    <h3>{{ titles }}</h3>
    <ul>
      <li v-for="(el, i) in comics" :key="i">{{ el }}</li>
    </ul>
  </div>
</template>

<script>
  export default {
    props: ['comics', 'titles'],
    name: 'Lists',
    data() {
      return {};
    },
  };
</script>

<style scoped>
  h3 {
    font-size: 1rem;
    margin-bottom: 10px;
    color: var(--white);
    margin-bottom: 15px 0;
  }
  ul {
    margin-bottom: 20px;
    margin-right: 30px;
  }
  li {
    color: var(--txtLessVisibile);
    font-size: 0.7rem;
    list-style: none;
    margin: 5px 0;
  }
</style>
