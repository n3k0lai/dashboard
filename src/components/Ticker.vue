<template>
  <div class="block" v-if="crypto.length > 0">
    <div class="block-cont">
      <div class="ticker"
           :class="{positive: crypto[0].change > 0, negative: crypto[0].change < 0}">
        <div class="label">{{ crypto[0].label + ' ' + crypto[0].val }}</div>
        <div class="change">{{ crypto[0].change }}</div>
      </div>
      <div class="ticker-wrap">
        <div class="ticker-scroll">
          <div class="ticker" 
               v-for="curr in crypto.slice(1)"
               :key="curr.label"
               :class="{positive: curr.change > 0, negative: curr.change < 0}">
            <div class="label">{{ curr.label + ' ' + curr.val }}</div>
            <div class="change">{{ curr.change }}</div>
          </div>
          <div class="ticker" 
               v-for="curr in crypto.slice(1)"
               :key="curr.label"
               :class="{positive: curr.change > 0, negative: curr.change < 0}">
            <div class="label">{{ curr.label + ' ' + curr.val }}</div>
            <div class="change">{{ curr.change }}</div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: 'ticker',
  data() {
    return {
      crypto: [] 
    }
  },
  mounted() {
    fetch('https://api.coinmarketcap.com/v1/ticker/?limit=10').then(res => res.json()).then(data => {
      console.log('BTC Res:', data)
      this.crypto = data.map(c => {
        return {
          label: c.symbol === 'BTC' ? 'Ƀ' : '$' + c.symbol,
          val: c.symbol === 'BTC' ? '$' + Math.floor(c.price_usd) : c.price_btc,
          change: parseFloat(c.percent_change_1h) }

      })
    }).catch((res) => console.log)
  } 
} 
</script>
<style lang="scss" scoped>

@-webkit-keyframes ticker {
  0% {
    -webkit-transform: translate3d(0, 0, 0);
            transform: translate3d(0, 0, 0);
    visibility: visible;
  }
  100% {
    -webkit-transform: translate3d(-100%, 0, 0);
            transform: translate3d(-100%, 0, 0);
  }
}

@keyframes ticker {
  0% {
    -webkit-transform: translate3d(0, 0, 0);
            transform: translate3d(0, 0, 0);
    visibility: visible;
  }
  100% {
    -webkit-transform: translate3d(-100%, 0, 0);
            transform: translate3d(-100%, 0, 0);
  }
}
.ticker {
  padding: 0 5px;

  .label {
    white-space: nowrap;
  }
  .change {
    text-align: right;
  }
  &.positive > .change {
    color: green;
  }
  &.negative > .change {
    color: red;
  }
}
.ticker-wrap {
  flex-grow: 1;
  width: 100%;
  overflow-x: hidden;
}
.ticker-scroll {
  width: 200%;
  display: flex;
  -webkit-animation-iteration-count: infinite;
          animation-iteration-count: infinite;
  -webkit-animation-timing-function: linear;
          animation-timing-function: linear;
  -webkit-animation-name: ticker;
          animation-name: ticker;
  -webkit-animation-duration: 30s;
          animation-duration: 30s;
}
</style>