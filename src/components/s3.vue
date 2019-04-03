<template>
  <div class="s3" :style="{height:computedHeight}">
    <div class="s3-img" :style="{backgroundPositionY:imgTrans}"></div>
        <h1 class="heading" :style="heading">MEDITATE ON A YOGO MAT</h1>
<div class="txt" :style="txt">
      NO MATTER YOU ARE DOING <br>
      A YOGA, CAMPING, YOU <br>
      CAN ALWAYS GET ALEXA OR <br>
      GOOGLE READY WITHOUT <br>
      PLUGGING INTO THE WALL
    </div>
        <dot :dot-style="styleObj" :bgcolor="'#000'" :lncolor="'white'"/>

  </div>
</template>

<script>
import dot from '@/components/dot.vue'
export default {
  name:'s3',
  props: ["s3-style"],
  components:{
    dot
  },
  data() {
    return {
      styleObj: this.s3Style
    };
  },
  computed:{
    computedHeight(){
      return (881/1280)*this.styleObj.win_width +'px'
    },
    imgTrans() {
      return "-" + (1765 / 1280) * this.styleObj.win_width + "px";
    },
     heading() {
      return {
        top: (118 / 1280) * this.styleObj.win_width + "px",
        fontSize: (18 / 1280) * this.styleObj.win_width + "px",
        letterSpacing: (4 / 1280) * this.styleObj.win_width + "px"
      };
    },
    txt() {
      return {
        width: (215 / 1280) * this.styleObj.win_width + "px",
        fontSize: (10/1280)*this.styleObj.win_width + "px",
        right:(180/1280)*this.styleObj.win_width +'px',
        bottom:(355/1280)*this.styleObj.win_width +'px',
        lineHeight:(22/1280)*this.styleObj.win_width+'px',
        letterSpacing:(3/1280)*this.styleObj.win_width+'px',
      };
    }
  }
}
</script>

<style scoped>
.s3 {
  width: 100vw;
  display: flex;
  justify-content: center;
  position: relative;
}
.s3-img {
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

  font-weight: 730;
}

.txt {
  position: absolute;
  font-weight: bold;
  text-align: start;
  color:#353535;
}
</style>
