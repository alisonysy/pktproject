<template>
  <div class="s7" :style="{height:computedHeight}">
    <div class="s7-img" :style="{backgroundPositionY:imgTrans}"></div>
    <h1 class="heading" :style="heading">PARAMETERS</h1>
    <div class="txt" :style="txt">
      <h3 :style="h3">SIZE AND WEIGHT</h3>
      DIMENSION:
      <br>26MM · 26MM
      <h3 :style="h3">THICKNESS:</h3>
      32MM
      <h3 :style="h3">WEIGHT:</h3>
      110G
    </div>
        <dot :dot-style="styleObj" :bgcolor="'#000'" :lncolor="'white'"/>

  </div>
</template>

<script>
import dot from "@/components/dot.vue";

export default {
  name: "s7",
  props: ["s7-style"],
  components: {
    dot
  },
  data() {
    return {
      styleObj: this.s7Style
    };
  },
  computed: {
    computedHeight() {
      return (885 / 1280) * this.styleObj.win_width + "px";
    },
    imgTrans() {
      return "-" + (5295 / 1280) * this.styleObj.win_width + "px";
    },
    heading() {
      return {
        top: (115 / 1280) * this.styleObj.win_width + "px",
        fontSize: (18 / 1280) * this.styleObj.win_width + "px",
        letterSpacing: (3 / 1280) * this.styleObj.win_width + "px"
      };
    },
    txt() {
      return {
        width: (105 / 1280) * this.styleObj.win_width + "px",
        fontSize: (8/1280)*this.styleObj.win_width + "px",
        top:(235/1280)*this.styleObj.win_width +'px',
        lineHeight:(35/1280)*this.styleObj.win_width+'px',
        letterSpacing:(2/1280)*this.styleObj.win_width+'px',
        right:(170/1280)*this.styleObj.win_width+'px',
      };
    },
    h3(){
      return {
                fontSize: (8/1280)*this.styleObj.win_width + "px",
          color:'#353535'
      }
    }
  }
};
</script>

<style scoped>
.s7 {
  width: 100vw;
  display: flex;
  justify-content: center;
  position: relative;
}

.s7-img {
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

.txt {
  position: absolute;
  font-weight: bold;
  text-align: start;
  color:#000;
}


</style>
