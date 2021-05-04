<template>
  <div>
    <span>FOLLOOW US</span>
    <ul>
      <li v-for="(item, i) in FootIcons" :key="i">
        <a href="#">
          <img :src="item.img" alt="item.nome" />
        </a>
      </li>
    </ul>
  </div>
</template>

<script>
  export default {
    name: 'FooterList',
    data() {
      return {
        FootIcons: [
          {
            nome: 'facebook',
            img: require('../assets/img/footer-facebook.png'),
          },
          {
            nome: 'twitter',
            img: require('../assets/img/footer-twitter.png'),
          },
          {
            nome: 'you tube',
            img: require('../assets/img/footer-youtube.png'),
          },
          {
            nome: 'pinterest',
            img: require('@/assets/img/footer-pinterest.png'),
          },
          {
            nome: 'periscope',
            img: require('../assets/img/footer-periscope.png'),
          },
        ],
      };
    },
  };
</script>

<style scoped>
  span {
    background-color: transparent;
    color: var(--brand);
    font-weight: bold;
  }
  ul,
  li {
    display: inline-block;
    margin-left: 13px;
  }
  img {
    vertical-align: middle;
    width: 30px;
  }
</style>
