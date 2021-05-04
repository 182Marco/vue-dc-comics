<template>
  <nav>
    <ul>
      <li v-for="(item, i) in links" :key="i">
        <a :href="item.link"> {{ item.nome.toUpperCase() }}</a>
      </li>
    </ul>
  </nav>
</template>

<script>
  export default {
    name: 'NavigateBar',
    data() {
      return {
        links: [
          {
            link: 'http://google.com',
            nome: 'CHARACTERS',
          },
          {
            link: 'http://google.com',
            nome: 'COMICS',
          },
          {
            link: 'http://google.com',
            nome: 'MOVIES',
          },
          {
            link: 'http://google.com',
            nome: 'TV',
          },
          {
            link: 'http://google.com',
            nome: 'GAMES',
          },
          {
            link: 'http://google.com',
            nome: 'collectibles',
          },
          {
            link: 'http://google.com',
            nome: 'videos',
          },
          {
            link: 'http://google.com',
            nome: 'fans',
          },
          {
            link: 'http://google.com',
            nome: 'news',
          },
          {
            link: 'http://google.com',
            nome: 'shop',
          },
        ],
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
</style>
