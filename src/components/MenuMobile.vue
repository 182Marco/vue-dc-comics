<template>
  <div class="wrap">
    <i @click="$emit('closeMenuMob')" class="fas fa-times x link-menMob"></i>
    <ul>
      <li class="link-menMob" v-for="(navLink, i) in navLinks" :key="i">
        <a :href="navLink.link">{{ navLink.nome.toUpperCase() }}</a>
      </li>
      <li @click="$emit('closeMenuMob')" class="link-menMob">
        <a class="close"> <i class="fas fa-times link-menMob"></i> CHIUDI </a>
      </li>
    </ul>
  </div>
</template>

<script>
  import navLinks from '@/data/navLinks.js';

  //   import dcComics from '@/data/dcComics.js';
  export default {
    // props: ['comic'],
    name: 'MenuMobile',
    data() {
      return {
        navLinks: navLinks,
      };
    },
  };
</script>

<style lang="scss" scoped>
  @import '@/scss/var';
  .wrap {
    height: 100vh;
    background-color: $bg2;
    position: relative;
    animation: slide-left 0.15s;
  }
  @keyframes slide-left {
    from {
      left: -100vw;
    }
    to {
      left: 0;
    }
  }

  ul {
    padding-top: 13vh;
    list-style: none;
  }
  .link-menMob {
    padding: 0.8vh 0 0 5vw;
    font-size: 2rem;
    color: $dark2;
    filter: drop-shadow(3px 3px 2px $black);
    cursor: pointer;
    &:hover {
      color: $brand;
      background-color: rgba(255, 255, 255, 0.04);
    }
    &:hover a {
      color: $brand;
    }
    &:hover a i {
      color: $brand;
    }

    a {
      color: $dark2;
      font-weight: 700;
      transition: color 0.3s;
    }
    &:last-child {
      padding-left: 0vw;
    }
    &.x {
      background-color: transparent;
      position: absolute;
      right: 5%;
      top: 3%;
    }
  }
  // azzerare colore di background sulla a
  .link-menMob > .close > i:hover {
    background-color: transparent;
  }

  // ****************
  i {
    transition: color 0.3s;
  }
  .close {
    padding-left: 5vw;
    transition: color 0.3s;
    &:hover i {
      color: $brand;
    }
  }
</style>
