<template>
  <div class="s8" :style="{height:computedHeight}">
    <div class="s8-bg" :style="bg"></div>
    <div class="s8-img" :style="{backgroundPositionY:imgTrans}"></div>
    <h1 class="heading" :style="heading">THE MAGBASE</h1>
    <div class="txt" :style="txt">
      PRE-ORDER NOW
    </div>
          <dot :dot-style="styleObj" :bgcolor="'#000'" :lncolor="'white'"/>

  </div>

</template>

<script>
import dot from "@/components/dot.vue";

export default {
  name: "s8",
  props: ["s8-style"],
  components: {
    dot
  },
  data() {
    return {
      styleObj: this.s8Style
    };
  },
  computed: {
    computedHeight() {
      return (885 / 1280) * this.styleObj.win_width + "px";
    },
    imgTrans() {
      return "-" + (6177 / 1280) * this.styleObj.win_width + "px";
    },
    heading() {
      return {
        top: (122 / 1280) * this.styleObj.win_width + "px",
        fontSize: (25 / 1280) * this.styleObj.win_width + "px",
        letterSpacing: (3 / 1280) * this.styleObj.win_width + "px"
      };
    },
    txt() {
      return {
        width: (130 / 1280) * this.styleObj.win_width + "px",
        fontSize: (10/1280)*this.styleObj.win_width + "px",
        bottom:(160/1280)*this.styleObj.win_width +'px',
        letterSpacing:(2/1280)*this.styleObj.win_width+'px',
      };
    },
    bg(){
      return {
        width:'calc(100% - '+(108/1280)*this.styleObj.win_width+'px)'
      }
    }
  }
};
</script>

<style scoped>
.s8 {
  width: 100vw;
  display: flex;
  justify-content: center;
  position: relative;
}
.s8-bg {
  background: #f5f6f8;
  height: 100%;
}
.s8-img {
  position: absolute;
  top: 0;
  left: 0;
  background-image: url("../assets/ptkMagbase-min.png");
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
.heading::after {
  content: "TM";
  position: absolute;
  font-size: 7px;
}

.txt {
  position: absolute;
  font-weight: bold;
  text-align: center;
  color:#000;
  left:50%;
  transform: translateX(-50%);
  cursor: pointer;
}

.txt::after{
  content:'';
  border-bottom:1px solid red;
  position: absolute;
      bottom: -5px;
    left: 50%;
    transform: translateX(-50%);
}

@media screen and (max-width:2500px) {
  .txt::after{
    width:160px;
  }
}


@media screen and (max-width:1600px) {
  .txt::after{
    width:130px;
  }
}

@media screen and (max-width:1300px) {
  .txt::after{
    width:110px;
  }
}

@media screen and (max-width:1000px) {
  .txt::after{
    width:70px;
  }
}
</style>
