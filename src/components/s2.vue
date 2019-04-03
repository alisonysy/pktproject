<template>
  <div class="s2" :style="{height:computedHeight}">
    <div class="s2-img" :style="{backgroundPositionY:imgTrans}"></div>
    <h1 class="heading" :style="heading">STICK TO THE WALL</h1>
    <div class="txt" :style="txt">
      BY ATTACHING WITH
      <span>MAGBASE</span> AND
      <span>MAGHIVE</span>, NOW YOU CAN MOUNT YOUR ECHO DOT, HOME MINI ON THE WALL WITH MAGNETS AND ASK THEM TO DO WHATEVER YOU LIKE.
    </div>
        <dot :dot-style="styleObj" :bgcolor="'#000'" :lncolor="'white'"/>

  </div>
</template>

<script>
import dot from "@/components/dot.vue";
export default {
  name: "s2",
  props: ["s2-style"],
  components:{
    dot
  },
  data() {
    return {
      styleObj: this.s2Style
    };
  },
  computed: {
    computedHeight() {
      return (885 / 1280) * this.styleObj.win_width + "px";
    },
    imgTrans() {
      return "-" + (880 / 1280) * this.styleObj.win_width + "px";
    },
    heading() {
      return {
        top: (100 / 1280) * this.styleObj.win_width + "px",
        fontSize: (18 / 1280) * this.styleObj.win_width + "px",
        letterSpacing: (4 / 1280) * this.styleObj.win_width + "px"
      };
    },
    txt() {
      return {
        width: (508 / 1280) * this.styleObj.win_width + "px",
        fontSize: (10/1280)*this.styleObj.win_width + "px",
        bottom:(120/1280)*this.styleObj.win_width +'px',
        lineHeight:(21/1280)*this.styleObj.win_width+'px',
        letterSpacing:(3/1280)*this.styleObj.win_width+'px',
      };
    }
  }
};
</script>

<style scoped>
.s2 {
  width: 100vw;
  display: flex;
  justify-content: center;
  position: relative;
}

.s2-img {
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
  text-align: center;
  color:#353535;
}

.txt span{
  position: relative;
  margin-right: 6px;
  color:#353535;
}

.txt span::after{
  position: absolute;
    top: -9px;
    right: -5px;
    content: 'TM';
    font-size: 5px;
    letter-spacing: 0;
}
</style>

