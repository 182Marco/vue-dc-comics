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

  ul {
    display: flex;
    justify-content: space-around;
    @include media-desk-first(desktop) {
      justify-content: flex-start;
    }
    align-items: center;
    list-style: none;
    flex-wrap: wrap;
  }

  li {
    font-size: 0.8rem;
    font-weight: 300;
    flex-wrap: wrap;
    @include media-desk-first(full-desktop) {
      font-size: 0.7rem;
    }
    @include media-desk-first(desktop) {
      width: 50%;
    }
    transition: scale 0.4s;
    a {
      display: block;
    }
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
    vertical-align: middle;
    &[alt='comic Shop Locator'] {
      width: 40px;
    }
  }
</style>
