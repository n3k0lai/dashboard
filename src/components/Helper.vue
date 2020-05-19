<template>
  <div class="block helper">
    <div class="block-cont">
      <input type="text" 
             placeholder="hello my friend"
             v-model="inputStr"
             @keyup.enter="handleSearch">
    </div>
  </div>
</template>
<script>

export default {
  name: 'helper',
  data() {
    return {
      inputStr: ''
      
    }
  },
  computed: {
    queryStr() {
      if (this.inputStr.length === 0)
        return ''
      else if (this.inputStr[0] !== '!')
        return 'https://google.com/search?q=' + encodeURIComponent(this.inputStr)

      let unparsed = this.inputStr.split(' ')
      let command = unparsed[0].slice(1)
      let textStr = encodeURIComponent(unparsed.slice(1).join(' '))
      switch (command) {
        case 'g':
          return 'https://google.com/search?q=' + textStr
        case 'm':
          return 'https://www.google.com/maps/place/' + textStr
        case 'i':
          return 'https://www.google.com/search?tbm=isch&q=' + textStr
        case 'yt':
          return 'https://youtube.com/results?search_query=' + textStr
        case 'ddg':
          return 'https://duckduckgo.com/?q=' + textStr
        case 'ddgn':
          return 'https://next.duckduckgo.com/?q=' + textStr
        case 'b':
          return 'https://www.bing.com/search?q=' + textStr
        case 'bi':
          return 'https://www.bing.com/images/search?q=' + textStr
        case 'bv':
          return 'https://www.bing.com/videos/search?q=' + textStr
        case 'start':
          return 'https://startpage.com/do/search?language=english&cat=web&query=' + textStr
        case 'wolf':
          return 'https://www.wolframalpha.com/input/?i=' + textStr
        case 'wiki':
          return 'https://wikipedia.org/wiki/Special:Search?search=' + textStr
        case 'vim':
          return 'http://vimeo.com/search?q=' + textStr
        case 'osm':
          return 'https://nominatim.openstreetmap.org/search.php?q=' + textStr
        default:
          return 'https://google.com/search?q=' + textStr
      }

    } 
  },
  methods: {
    handleSearch() {
      if (this.queryStr.length > 0)
        window.location = this.queryStr
    } 
  } 
}
</script>
<style lang="scss" scoped>
.helper {
  flex-grow: 1;
  input {
    width: 100%;
  }
}
</style>