<template>
  <div class="block splash">
    <div class="block-cont">
      <div v-if="asset.type === 'img'" 
           class="image-cont"
           :style="'background-image: url(' + asset.url + ');'">
      </div>
      <video v-if="asset.type === 'vid'"
             muted
             autoplay
             loop>
        <source :src="asset.url" type="video/mp4">
      </video>
    </div>
  </div>
</template>
<script>
const splashes = [{
  type: 'img',
  url: '../../assets/perfectblue.jpg' 
}, {
  type: 'vid',
  url: '../../assets/sad.mp4' 
}]

export default {
  name: 'splash',
  data() {
    return {
      asset: splashes[Math.floor(Math.random() * splashes.length)] 
    }
  } 
}
  
</script>
<style lang="scss" scoped>
.splash {
  width: 50%;
  height: 200px;
  position: relative;

  .block-cont {
    height: 100%;
    position: relative;
    overflow: hidden;
  }
  .image-cont {
    background-repeat: no-repeat;
    background-size: cover;
    background-position: center;
    position: absolute;
    width: 100%;
    height: 100%;
    top: 0;
    left: 0;
  }
  video {
    position: absolute;
    width: 100%;
    height: 100%;
    top: 0;
    left: 0;
    object-fit: cover;
  }
}
</style>