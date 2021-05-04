<template>
  <div id="app">
    <div class="stripe1"></div>
    <div class="stripe2">
      <div class="cont">
        <!-- logo -->
        <img class="logo" src="@/assets/img/dc-logo.png" alt="logo" />
        <NavigateBar></NavigateBar>
      </div>
    </div>
    <div class="stripe3">
      <div class="cont">
        <h2>-->content goese here</h2>
      </div>
    </div>
    <div class="stripe4"></div>
    <HelloWorld msg="Welcome to Your Vue.js App" />
  </div>
</template>

<script>
  import NavigateBar from './components/NavigateBar.vue';

  export default {
    name: 'App',
    components: {
      NavigateBar,
    },
  };
</script>

<style>
  @import url('https://fonts.googleapis.com/css2?family=Roboto:wght@300;400;500;700;900&display=swap');

  :root {
    --brand: #1e82f6;
    --white: #fff;
    --black: #000;
  }

  * {
    font-family: 'Roboto', sans-serif;
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }

  a {
    text-decoration: none;
  }

  #app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
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
    height: 12vh;
  }

  .stripe2 > .cont {
    display: flex;
    align-items: center;
    justify-content: space-between;
  }

  img.logo {
    width: 75px;
  }

  .stripe3 > .cont {
    display: flex;
    align-items: center;
    color: var(--white);
  }

  .stripe4 {
    background-color: var(--brand);
    height: 16vh;
  }

  .cont {
    height: 100%;
    width: 80%;
    margin: 0 auto;
  }
</style>
