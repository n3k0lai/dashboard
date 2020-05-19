<template>
<div class="block">
  <div class="block-cont" style="line-height: 23px;">
    🍀 
    <a v-for="chan in chans"
       :key="chan.url"
       :href="chan.url" 
       target="_self" 
       class="button chan">
      /{{ chan.letter }}/
    </a>
  </div>
</div>
</template>
<script>
const chans = [{
  letter: 'b',
  url: 'https://4chan.org/b/catalog' 
}, {
  letter: 'g',
  url: 'https://4chan.org/g/catalog' 
}, {
  letter: 'a',
  url: 'https://4chan.org/a/catalog' 
}, {
  letter: 'u',
  url: 'https://dangeru.us/all' 
}]
  
export default {
  name: 'chan',
  data() {
    return {
      chans: chans 
    }
  } 
}
</script>
<style lang="scss" scoped>
.button {
  color: white;
  margin-left: 10px;
  text-decoration: none;
  &.chan {
    transition: 350ms ease all;
    &:hover {
      color: #45be41;
    }
  }
}
</style>