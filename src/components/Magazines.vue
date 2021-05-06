<template>
    <div class="wrap" >
      <div class="box">
        <img :src="comic.thumb" :alt="comic.series" />
      </div>
      <p>{{ comic.series }}</p>
    </div>
</template>

<script>
  import dcComics from '@/data/dcComics.js';
  export default {
    props: ['comic'],
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
      .wrap{
      margin-right:20px;
      flex-basis: calc(100% / 6 - 20px);
      // overflow: hidden;
      @include media-desk-first(desktop) {
        flex-basis: calc(100% / 4 - 20px);
      }
      @include media-desk-first(tablet) {
        flex-basis: calc(100% / 3 - 20px);
        &:first-child,
        &:nth-child(2),
        &:nth-child(3) {
          margin-top: 30px;
        }
        &:nth-child(10),
        &:nth-child(11),
        &:last-child {
          margin-bottom: 50px;
        }
      }
      @include media-desk-first(s-tablet) {
        flex-basis: calc(100% / 2 - 20px);
        &:nth-child(9),
        &:nth-child(10),
        &:nth-child(11),
        &:last-child {
          display: none;
        }
      }
      @include media-desk-first(s-phone) {
        margin: 0;
        flex-basis: 100%;
        &:nth-child(4),
        &:nth-child(5),
        &:nth-child(6),
        &:nth-child(7),
        &:nth-child(8) {
          display: none;
        }
      }
    }

    .box {
      height: 170px;
      overflow: hidden;
      @include media-desk-first(s-tablet) {
        height: 220px;
      }
      @include media-desk-first(s-phone) {
        height: 400px;
      }
      img {
        width: 100%;
      }
    }
    p {
      color: $white;
      text-transform: uppercase;
      margin-top: 10px;
      font-weight: bold;
      font-size: 0.63rem;
      @include media-desk-first(s-phone) {
      font-size: 1rem;
      text-align: center
  }
    }

</style>
