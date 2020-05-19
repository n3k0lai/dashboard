<template>
  <div id="home">
    <div class="row">
      <helper></helper>
      <quik-links></quik-links>
      <chan></chan>
    </div>
    <div class="row">
      <quote></quote>
      <splash></splash>
    </div>
    <div class="row">
      <ticker></ticker>
    </div>
  </div>
</template>
<script>
import quikLinks from './components/QuikLinks.vue'
import chan from './components/Chan.vue'
import splash from './components/Splash.vue'
import quote from './components/Quote.vue'
import helper from './components/Helper.vue'
import ticker from './components/Ticker.vue'

export default {
  name:'home-sweet-home',
  components: {
    helper,
    quikLinks,
    chan,
    quote,
    splash,
    ticker
  } 
}
</script>
<style lang="scss">
* {
  box-sizing: border-box;
}

body, html {
  width: 100%;
  height: 100%;
  margin: 0;
  padding: 0;
  position: relative;
}

body {
  font-family: "Lucida Console", Monaco, monospace;
  display: flex;
  justify-content: center;
  align-items: center;
  color: #fff;
  background-color: #333;
}

#app {
  width: 100%;
  max-width: 800px;
  padding: 10px;
  .row {
    display: flex;
    .block {
      max-width: 100%;
      padding: 10px;
      .block-cont {
        padding: 20px;
        border: 1px solid white;
        display: flex;
        max-width: 100%;
      }
    }
  }
}
</style>