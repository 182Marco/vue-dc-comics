<template>
  <div id="app">
    <div class="stripe2">
      <div class="cont">
        <!-- logo -->
        <img class="logo" src="@/assets/img/dc-logo.png" alt="logo" />
        <NavigateBar />
      </div>
    </div>
    <div class="stripe3">
      <!-- jumbotron -->
      <img class="jumbo" src="@/assets/img/jumbotron.jpg" alt="jumbotron.jpg" />
    </div>
    <!-- lista fumetti -->
    <div class="stripe3dot1">
      <div class="cont">
        <Btn class="jumboBtn" :fullBg="fullBg" :content="BtnJumbo" />
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
          <img src="@/assets/img/dc-logo-bg.png" alt="big-logo" />
        </div>
      </div>
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
  import MiddleLinks from './components/MiddleLinks.vue';
  import FooterList from '@/components/FooterList.vue';
  import Btn from './components/Btn.vue';
  import Lists from './components/Lists.vue';
  // dati
  import dcComics from './data/comics.js';
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
    },
    data() {
      return {
        fullBg: true,
        BtnJumbo: 'CURRENT SERIES',
        BtnFooter: 'SIGN UP NOW!',
        titles: ['DC COMICS', 'SHOP', 'DC', 'SITES'],
        comics: dcComics,
        shops: ['Shop DC', 'Shop DC collections'],
        dcs: dcs,
        sites: sites,
      };
    },
  };
</script>

<style>
  @import url('https://fonts.googleapis.com/css2?family=Roboto:wght@300;400;500;700;900&display=swap');

  :root {
    --brand: #1e82f6;
    --white: #fff;
    --black: rgb(182, 172, 172);
    --dark: #1c1c1c;
    --bg2: #303030;
    --bg3: #252525;
    --txtLessVisibile: #999;
  }

  * {
    font-family: 'Roboto', sans-serif;
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }
  #app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    height: 100vh;
  }
  .cont {
    height: 100%;
    width: 80%;
    max-width: 1080px;
    margin: 0 auto;
  }

  a {
    text-decoration: none;
  }

  .stripe2 {
    height: 11vh;
  }

  .stripe3 {
    overflow: hidden;
    height: 30.5vh;
  }

  .stripe2 > .cont {
    display: flex;
    align-items: center;
    justify-content: space-between;
  }

  .logo {
    width: 60px;
  }

  .stripe3 > .cont {
    background-color: var(--black);
    display: flex;
    align-items: center;
    color: var(--white);
  }
  .stripe3dot1 {
    height: 50vh;
    background-color: var(--dark);
  }
  .stripe3dot1 > .cont {
    position: relative;
  }
  .stripe3dot1 > .cont > .jumboBtn {
    position: absolute;
    left: 0;
    /* non si può usare translate (lo uso poi in animazione, 
    altrimenti si influenzano e fa effetti strani durante
     l'animazione) */
    top: -19.5px;
  }

  img.jumbo {
    width: 100vw;
  }

  .stripe4 {
    background-color: var(--brand);
    height: 15vh;
  }

  main {
    height: 42vh;
    background-image: url('./assets/img/footer-bg.jpg');
  }

  main > .cont {
    position: relative;
    overflow: hidden;
  }

  .list-wrap {
    display: flex;
    height: 75%;
    margin-top: 4.3%;
    overflow-anchor: ;
  }

  img[alt='big-logo'] {
    position: absolute;
    right: 0;
    top: 50%;
    transform: translateY(-50%);
    width: 520px;
  }

  footer {
    background-color: var(--bg2);
    height: 12vh;
  }
  footer > .cont {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
  .low-foot {
    height: 2vh;
    background-color: var(--bg3);
  }
</style>
