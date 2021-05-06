<template>
  <div id="app">
    <div class="stripe2">
      <div class="cont">
        <!-- logo -->
        <img class="logo" src="@/assets/img/dc-logo.png" alt="logo" />
        <NavigateBar class="navDesk">
          <Hamburger class="hamburger"> </Hamburger>
        </NavigateBar>
      </div>
    </div>
    <div class="stripe3">
      <!-- jumbotron -->
      <img class="jumbo" src="@/assets/img/jumbotron.jpg" alt="jumbotron.jpg" />
    </div>
    <!-- lista fumetti -->
    <div class="stripe3dot1">
      <div class="cont">
        <Btn class="jumboBtn" :fullBg="true" :content="BtnJumbo" />
        <div class="comic-box">
          <Magazines
            class="magazines"
            v-for="(comic, i) in dcComics"
            :key="i"
            :comic="comic"
          />
        </div>
        <Btn class="jumboBtn btnMore" :fullBg="fullBg" :content="BtnMore" />
      </div>
    </div>
    <div class="stripe4">
      <!-- links under jumbo -->
      <MiddleLinks />
    </div>
    <main>
      <div class="cont">
        <div class="list-wrap">
          <div>
            <!-- liste sulla parte con bg img scura -->
            <Lists :comics="comics" :titles="titles[0]" />
            <Lists :comics="shops" :titles="titles[1]" />
          </div>
          <Lists :comics="dcs" :titles="titles[2]" />
          <Lists :comics="sites" :titles="titles[3]" />
        </div>
      </div>
      <img src="@/assets/img/dc-logo-bg.png" alt="big-logo" />
    </main>
    <!-- footer -->
    <footer>
      <div class="cont">
        <Btn :content="BtnFooter" />
        <FooterList />
      </div>
    </footer>
    <div class="low-foot"></div>
  </div>
</template>

<script>
  import NavigateBar from './components/NavigateBar.vue';
  import Hamburger from './components/Hamburger.vue';
  import MiddleLinks from './components/MiddleLinks.vue';
  import FooterList from '@/components/FooterList.vue';
  import Btn from './components/Btn.vue';
  import Lists from './components/Lists.vue';
  import Magazines from './components/Magazines.vue';
  // dati
  import dcComics from './data/dcComics.js';
  import comics from './data/comics.js';
  import dcs from './data/dcs.js';
  import sites from './data/sites.js';

  export default {
    name: 'App',
    components: {
      NavigateBar,
      MiddleLinks,
      Btn,
      FooterList,
      Lists,
      Magazines,
      Hamburger,
    },
    data() {
      return {
        fullBg: true,
        BtnJumbo: 'CURRENT SERIES',
        BtnFooter: 'SIGN UP NOW!',
        BtnMore: 'LOAD MORE',
        dcComics: dcComics,
        titles: ['DC COMICS', 'SHOP', 'DC', 'SITES'],
        comics: comics,
        shops: ['Shop DC', 'Shop DC collections'],
        dcs: dcs,
        sites: sites,
      };
    },
  };
</script>

<style lang="scss">
  @import url('https://fonts.googleapis.com/css2?family=Roboto:wght@300;400;500;700;900&display=swap');
  @import './scss/mixins';
  @import './scss/var';
  @import './scss/reset';
  @import './scss/utility';
  @import './scss/navbar';
  @import './scss/jumbo';
  @import './scss/footer';

  #app {
    height: 100vh;
    width: 100vw;
  }
</style>
