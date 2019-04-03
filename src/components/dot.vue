<template>
  <div class="dot-wrapper" :style="{width:width,height:height,bottom:bottom}">
    <div class="line" :style="lineStyle"></div>
  </div>
</template>

<script>
export default {
  name:'dot',
  props:['dot-style'],
  data(){
    return {
      styleObj:this.dotStyle,
      dotWidth:0,
    }
  },
  computed:{
    width(){
      this.dotWidth=(15/1280)*this.styleObj.win_width;
      return (15/1280)*this.styleObj.win_width + 'px';
    },
    height(){
      return (25/1280)*this.styleObj.win_width + 'px';
    },
    bottom(){
      return (35/1280)*this.styleObj.win_width+'px';
    },
    lineStyle(){
      return {
        height:(4/this.dotWidth)*this.dotWidth + 'px',
        top:(5/this.dotWidth)*this.dotWidth + 'px'
      }
    }
  }
}
</script>

<style scoped>
.dot-wrapper{
  position: absolute;
  left:50%;
  transform:translateX(-50%);
  background:#fff;
  border-radius: 10px / 10px;
}

.line{
  position:absolute;
  content:'';
  border-left: 1px solid black;
  left:50%;
    transform: translateX(-50%);
}
</style>
