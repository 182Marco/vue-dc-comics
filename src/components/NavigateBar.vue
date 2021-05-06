<template>
  <nav>
    <ul>
      <li v-for="(item, i) in navLinks" :key="i">
        <a
          class="navLink"
          :href="item.link"
          :class="{ active: item.active == true }"
        >
          {{ item.nome.toUpperCase() }}</a
        >
      </li>
      <li>
        <slot></slot>
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
  ul {
    display: flex;
  }
  ul,
  nav,
  li,
  a {
    height: 100%;
  }

  li {
    display: inline-block;
    padding: 0 0.7vw;
    font-size: 0.7rem;
    font-weight: 700;
    &:last-child {
      padding-right: 0;
      @include flex();
    }
    .navLink {
      color: $black;
      display: flex;
      align-items: center;
      border-bottom: 5px solid transparent;
      @include media-desk-first(sm-desktop) {
        font-size: 0.6rem;
      }
      transition: all 0.2s;
      &:hover {
        color: $brand;
        border-bottom: 5px solid $brand;
      }
      .hamburger-slot > a:hover {
        border: 0;
      }
      &.active {
        color: $brand;
        border-bottom: 5px solid $brand;
      }
    }
    // rimuovere dal flusso i link quando entra l'hamburger
    @include media-desk-first(xl-tablet) {
      display: none;
    }
  }
</style>
