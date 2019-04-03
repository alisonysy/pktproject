<template>
  <div class="dot-wrapper" :style="{width:width,height:height,bottom:bottom,backgroundColor:dotcolor}">
    <div class="line" :style="lineStyle"></div>
  </div>
</template>

<script>
export default {
  name:'dot',
  props:['dot-style','bgcolor','lncolor'],
  data(){
    return {
      styleObj:this.dotStyle,
      dotWidth:0,
      dotcolor:this.bgcolor,
      lineColor:this.lncolor
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
      return (38/1280)*this.styleObj.win_width+'px';
    },
    lineStyle(){
      return {
        height:(4/this.dotWidth)*this.dotWidth + 'px',
        top:(5/this.dotWidth)*this.dotWidth + 'px',
        borderLeft:'1px solid '+this.lineColor
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
  border-radius: 10px / 10px;
}

.line{
  position:absolute;
  content:'';
  left:50%;
    transform: translateX(-50%);
}
</style>
