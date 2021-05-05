<template>
  <div id="app">
    <div class="stripe1"></div>
    <div class="stripe2">
      <div class="cont">
        <!-- logo -->
        <img class="logo" src="@/assets/img/dc-logo.png" alt="logo" />
        <NavigateBar />
      </div>
    </div>
    <div class="stripe3">
      <div class="cont">
        <h2>-->content goese here</h2>
      </div>
    </div>
    <div class="stripe4">
      <MiddleLinks />
    </div>
    <main>
      <div class="cont">
        <div class="list-wrap">
          <div>
            <Lists :comics="comics" :titles="titles[0]" />
            <Lists :comics="shops" :titles="titles[1]" />
          </div>
          <Lists :comics="dcs" :titles="titles[2]" />
          <Lists :comics="sites" :titles="titles[3]" />
          <img src="@/assets/img/dc-logo-bg.png" alt="big-logo" />
        </div>
      </div>
    </main>
    <footer>
      <div class="cont">
        <Btn />
        <FooterList />
      </div>
    </footer>
    <div class="low-foot"></div>
  </div>
</template>

<script>
  import NavigateBar from './components/NavigateBar.vue';
  import MiddleLinks from './components/MiddleLinks.vue';
  import FooterList from './components/FooterList.vue';
  import Btn from './components/Btn.vue';
  import Lists from './components/Lists.vue';

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
        titles: ['DC COMICS', 'SHOP', 'DC', 'SITES'],
        comics: [
          'Characters',
          'Comics',
          'Movies',
          'TV',
          'Games',
          'Videos',
          'News',
        ],
        shops: ['Shop DC', 'Shop DC collections'],
        dcs: [
          'Terms of use',
          'Privacy Policy (New)',
          'Ad Choices',
          'Advertising',
          'Jobs',
          'Subscriptions',
          'Talent Workshops',
          'CPSC Certificates',
          'Ratings',
          'Shop Help',
          'Contact us',
        ],
        sites: [
          'DC',
          'MAD Magazines',
          'DC Kids',
          'DC Universe',
          'DC Power Visa',
        ],
      };
    },
  };
</script>

<style>
  @import url('https://fonts.googleapis.com/css2?family=Roboto:wght@300;400;500;700;900&display=swap');

  :root {
    --brand: #1e82f6;
    --white: #fff;
    --black: #000;
    --bg2: #303030;
    --bg3: #252525;
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

  .stripe1,
  .stripe3 {
    background-color: #000;
  }
  .stripe1 {
    height: 9vh;
  }
  .stripe2,
  .stripe3 {
    height: 10vh;
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
    display: flex;
    align-items: center;
    color: var(--white);
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
