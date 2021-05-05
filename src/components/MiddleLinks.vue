<template>
  <ul class="cont">
    <li v-for="(item, i) in links" :key="i">
      <a :href="item.link">
        <img :src="item.img" :alt="item.nome" />
        <span>{{ item.nome.toUpperCase() }}</span>
      </a>
    </li>
  </ul>
</template>

<script>
  import links from '@/data/links.js';

  export default {
    name: 'MiddleLinks',
    data() {
      return {
        links: links,
      };
    },
  };
</script>

<style lang="scss" scoped>
  @import '@/scss/var';
  ul,
  nav,
  li,
  a {
    height: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
  }

  li {
    display: inline-block;
    padding: 0 2vw;
    font-size: 0.8rem;
    font-weight: 300;
    span {
      color: $white;
    }
  }

  img {
    width: 50px;
    padding-right: 8px;
    &[alt='comic Shop Locator'] {
      width: 40px;
    }
  }
</style>
