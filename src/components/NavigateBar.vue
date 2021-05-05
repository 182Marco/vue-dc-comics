<template>
  <nav>
    <ul>
      <li v-for="(item, i) in navLinks" :key="i">
        <a :href="item.link" :class="{ active: item.active == true }">
          {{ item.nome.toUpperCase() }}</a
        >
      </li>
    </ul>
  </nav>
</template>

<script>
  import navLinks from '@/data/navLinks.js';

  export default {
    name: 'NavigateBar',
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

  ul,
  nav,
  li,
  a {
    height: 100%;
  }
  a {
    height: 98%;
  }
  li {
    display: inline-block;
    padding: 0 0.7vw;
    font-size: 0.7rem;
    font-weight: 700;
    &:last-child {
      padding-right: 0;
    }
    a {
      color: $black;
      display: flex;
      align-items: center;
      border-bottom: 2px solid transparent;
      @include media-desk-first(sm-desktop) {
      font-size: 0.6rem
      }
      transition: all 0.2s;
      &:hover {
        color: $brand;
        border-bottom: 5px solid $brand;
      }
      &.active {
        color: $brand;
        border-bottom: 5px solid $brand;
      }
    }
  }
</style>
