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
  import FootIcons from '@/data/FootIcons.js';

  export default {
    name: 'FooterList',
    data() {
      return {
        FootIcons: FootIcons,
      };
    },
  };
</script>

<style lang="scss" scoped>
  @import '@/scss/var';
  span {
    background-color: transparent;
    color: $brand;
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
    transition: scale 0.2s;
    &:hover {
      transform: scale(1.08);
    }
  }
</style>
