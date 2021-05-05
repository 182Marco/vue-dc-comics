<template>
  <section>
    <div class="wrap" v-for="(e, i) in dcComics" :key="i">
      <div class="box">
        <img :src="e.thumb" :alt="e.series" />
      </div>
      <p>{{ e.series }}</p>
    </div>
  </section>
</template>

<script>
  import dcComics from '@/data/dcComics.js';
  export default {
    name: 'Magazines',
    data() {
      return {
        dcComics: dcComics,
      };
    },
  };
</script>

<style lang="scss" scoped>
  @import '@/scss/mixins';
  @import '@/scss/var';
  section {
    display: flex;
    flex-wrap: wrap;
    padding-top: 6vh;
  }
  .wrap {
    display: flex;
    flex-direction: column;
    margin-right: 20px;
    margin-bottom: 40px;
    flex-basis: calc(100% / 6 - 20px);
      @include media-desk-first(desktop) {
      flex-basis: calc(100% / 4 - 20px);
      }
    cursor: pointer;
    .box {
      height: 170px;
      overflow: hidden;
      img {
        object-fit: contain;
        object-position: 20% 100%;
        width: 100%;
      }
    }
    p {
      color: $white;
      text-transform: uppercase;
      margin-top: 10px;
      font-weight: bold;
      font-size: 0.63rem;
    }
  }
</style>
