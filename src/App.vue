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
      <img class="bg" src="@/assets/img/footer-bg.jpg" alt="footer-bg" />
    </main>
    <footer></footer>
  </div>
</template>

<script>
  import NavigateBar from './components/NavigateBar.vue';
  import MiddleLinks from './components/MiddleLinks.vue';

  export default {
    name: 'App',
    components: {
      NavigateBar,
      MiddleLinks,
    },
  };
</script>

<style>
  @import url('https://fonts.googleapis.com/css2?family=Roboto:wght@300;400;500;700;900&display=swap');

  :root {
    --brand: #1e82f6;
    --white: #fff;
    --black: #000;
    --bg2: #21232b;
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
  }

  .bg {
    height: 100%;
    width: 100%;
    object-fit: cover;
  }

  footer {
    background-color: var(--bg2);
    height: 14vh;
  }
</style>
