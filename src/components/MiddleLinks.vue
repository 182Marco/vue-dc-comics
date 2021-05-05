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
  @import '@/scss/mixins';
  @import '@/scss/var';

  nav,
  li,
  a {
    display: flex;
    align-items: center;
    justify-content: center;
  }
 
 ul{
    display: flex;
    justify-content: space-around;
    align-items:center;
 }

  li {
    font-size: 0.8rem;
    font-weight: 300;
    @include media-desk-first(full-desktop) {
    font-size: 0.7rem;
    }    
    @include media-desk-first(desktop) {
    display:block;
    flex-wrap: wrap;
    width: 50vw;
    }
    flex-wrap: nowrap;
    transition: scale 0.4s;
    // flex-wrap: nowrap;
    &:hover {
      transform: scale(1.02);
    }
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
