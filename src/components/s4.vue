<template>
  <div class="s4" :style="{height:computedHeight}">
    <div class="s4-img" :style="{backgroundPositionY:imgTrans}"></div>
        <h1 class="heading" :style="heading">
          WIRELESS CHARGING ANY <br>
          QI SUPPORTED DEVICES
        </h1>
        <dot :dot-style="styleObj" :bgcolor="'#000'" :lncolor="'white'"/>

  </div>
</template>

<script>
import dot from '@/components/dot.vue'

export default {
  name:'s4',
  props:['s4-style'],
  components:{
    dot
  },
  data() {
    return {
      styleObj: this.s4Style
    };
  },
  computed:{
    computedHeight(){
      return (885/1280)*this.styleObj.win_width +'px'
    },
    imgTrans() {
      return "-" + (2640 / 1280) * this.styleObj.win_width + "px";
    },
    heading() {
      return {
        top: (100 / 1280) * this.styleObj.win_width + "px",
        fontSize: (18 / 1280) * this.styleObj.win_width + "px",
        letterSpacing: (4 / 1280) * this.styleObj.win_width + "px",
        lineHeight:(24/1280)* this.styleObj.win_width + "px",
      };
    },
  }
}
</script>

<style scoped>
.s4 {
  width: 100vw;
  display: flex;
  justify-content: center;
  position: relative;
}
.s4-img {
  position: absolute;
  top: 0;
  left: 0;
  background-image: url("../assets/ptkMagbase.png");
  background-size: 100%;
  width: 100%;
  height: 100%;
  background-origin: border-box;
}
.heading {
  position: absolute;
  left: 50%;
  transform: translateX(-50%);
  color: #353535;
  text-align: center;
  font-weight: 730;
}

</style>
