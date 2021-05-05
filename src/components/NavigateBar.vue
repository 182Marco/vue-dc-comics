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

<style scoped>
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
  }
  li:last-child {
    padding-right: 0;
  }

  a {
    color: var(--black);
    display: flex;
    align-items: center;
    border-bottom: 2px solid transparent;
    transition: all 0.2s;
  }
  a:hover {
    color: var(--brand);
    border-bottom: 5px solid var(--brand);
  }
  a.active {
    color: var(--brand);
    border-bottom: 5px solid var(--brand);
  }
</style>
