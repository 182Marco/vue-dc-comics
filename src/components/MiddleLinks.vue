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
  export default {
    name: 'MiddleLinks',
    data() {
      return {
        links: [
          {
            link: 'http://google.com',
            nome: 'digital comics',
            img: require('../assets/img/buy-comics-digital-comics.png'),
          },
          {
            link: 'http://google.com',
            nome: 'DC merchandise',
            img: require('../assets/img/buy-comics-merchandise.png'),
          },
          {
            link: 'http://google.com',
            nome: 'subscription',
            img: require('../assets/img/buy-comics-subscriptions.png'),
          },
          {
            link: 'http://google.com',
            nome: 'comic Shop Locator',
            img: require('../assets/img/buy-comics-shop-locator.png'),
          },
          {
            link: 'http://google.com',
            nome: 'dc power visa',
            img: require('../assets/img/buy-dc-power-visa.svg'),
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
    display: flex;
    align-items: center;
    justify-content: center;
  }

  li {
    display: inline-block;
    padding: 0 2vw;
    font-size: 0.8rem;
    font-weight: 300;
  }

  span {
    color: var(--white);
  }

  img {
    width: 50px;
    padding-right: 8px;
  }

  img[alt='comic Shop Locator'] {
    width: 40px;
  }
</style>
