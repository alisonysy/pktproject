<template>
  <div class="s6" :style="{height:computedHeight}">
    <div class="s6-bg"></div>

    <div class="s6-img" :style="{backgroundPositionY:imgTrans}"></div>
    <h1 class="heading" :style="heading">KEY FEATURES</h1>
    <div class="desc" :style="desc">
      <div class="desc1" :style="desc1">
        <div class="img" :style="img"></div>
        <h3 :style="h3">OVER-CHARGED PROTECTION</h3>
        <p :style="p">
          INTELLIGENT BATTERY MANAGEMENT SYSTEM ALLOWS
          <br>THE USER TO KEEP THE DEVICE BEING CHARGED
          <br>CONTINUOUSLY WITHOUT DAMAGING THE BATTERY.
        </p>
      </div>
      <div class="desc2" :style="desc1">
        <div class="img" :style="img"></div>
        <h3 :style="h3">MAGNETIC ATTACHABLE AND DETACHABLE</h3>
        <p :style="p">
          MAGNETS ARE EMBEDDED INSIDE, ALLOWS IT TO BE ATTACHED
          <br>ON MAGHIVE WITHOUT ADHESIVE NEEDED, AND YOU CAN
          <br>ATTACH AN ECHO DOT, OR GOOGLE HOME MINI EASILY AND
          <br>SECURELY WITH A PIECE OF METAL PLATE SUPPLIED.
        </p>
      </div>
      <div class="desc3" :style="desc1">
        <div class="img" :style="img"></div>
        <h3 :style="h3">ANTI-SLIPPERY DESIGN</h3>
        <p :style="p">
          COATED WITH FABRIC OF ARAMID FIBER BOTH ON THE TOP AND
          <br>BOTTOM, DEVICES CAN BE SECURELY ATTACHED TO THE MAGBASE, AND
          <br>THE MAGBASE CAN BE SECURELY MOUNTED ON THE WALL.
        </p>
      </div>
    </div>
    <div class="dots" :style="dots">
      <div class="dot"></div>
      <div class="dot"></div>
      <div class="dot"></div>
    </div>
    <dot :dot-style="styleObj" :bgcolor="'#000'" :lncolor="'white'"/>
  </div>
</template>

<script>
import dot from "@/components/dot.vue";

export default {
  name: "s6",
  props: ["s6-style"],
  components: {
    dot
  },
  data() {
    return {
      styleObj: this.s6Style
    };
  },
  computed: {
    computedHeight() {
      return (880 / 1280) * this.styleObj.win_width + "px";
    },
    imgTrans() {
      return "-" + (4415 / 1280) * this.styleObj.win_width + "px";
    },
    heading() {
      return {
        top: (100 / 1280) * this.styleObj.win_width + "px",
        fontSize: (18 / 1280) * this.styleObj.win_width + "px",
        letterSpacing: (3 / 1280) * this.styleObj.win_width + "px"
      };
    },
    desc() {
      return {
        width: (500 / 1280) * this.styleObj.win_width + "px",
        height: (342 / 1280) * this.styleObj.win_width + "px",
        left: (142 / 1280) * this.styleObj.win_width + "px",
        top: (270 / 1280) * this.styleObj.win_width + "px"
      };
    },
    desc1() {
      return {
        height: (114 / 1280) * this.styleObj.win_width + "px"
      };
    },
    img() {
      return {
        width: (100 / 1280) * this.styleObj.win_width + "px",
        height: (113 / 1280) * this.styleObj.win_width + "px"
      };
    },
    h3() {
      return {
        marginTop: (23 / 1280) * this.styleObj.win_width + "px",
        fontSize: (11 / 1280) * this.styleObj.win_width + "px",
        marginBottom: (13 / 1280) * this.styleObj.win_width + "px",
        letterSpacing: (2 / 1280) * this.styleObj.win_width + "px"
      };
    },
    p() {
      return {
        marginBottom: (28 / 1280) * this.styleObj.win_width + "px",
        fontSize: (7 / 1280) * this.styleObj.win_width + "px",
        lineHeight: (13 / 1280) * this.styleObj.win_width + "px",
        letterSpacing: (2 / 1280) * this.styleObj.win_width + "px"
      };
    },
    dots() {
      return {
        //width: (39 / 1280) * this.styleObj.win_width + "px",
        paddingTop: (2 / 1280) * this.styleObj.win_width + "px",
        paddingBottom: (2 / 1280) * this.styleObj.win_width + "px",
        right: (350 / 1280) * this.styleObj.win_width + "px",
        bottom: (230 / 1280) * this.styleObj.win_width + "px"
      };
    },
    dot() {
      return {
        width: (3 / 1280) * this.styleObj.win_width + "px",
        height: (3 / 1280) * this.styleObj.win_width + "px"
      };
    }
  }
};
</script>

<style scoped>
.s6 {
  width: 100vw;
  display: flex;
  justify-content: center;
  position: relative;
}
.s6-bg {
  width: calc(100% - 108px);
  background: #f5f6f8;
  height: 100%;
}
.s6-img {
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
.desc {
  position: absolute;
}
.desc1 {
  background: #000;
  color: #fff;
  width: 100%;
  text-align: right;
}
.desc1 .img {
  background-image: url("../assets/battery.png");
  background-size: cover;
  float: right;
}
.desc1 h3,
.desc1 p {
  text-align: right;
  color: #fff;
  display: inline-block;
}

.desc2,
.desc3 {
  background: #fff;
  width: 100%;
  text-align: right;
}
.desc2 .img {
  background-image: url("../assets/mag.png");
  background-size: cover;
  float: right;
}
.desc2 h3,
.desc2 p {
  text-align: right;
  color: #353535;
  display: inline-block;
}

.desc3 .img {
  background-image: url("../assets/prohibit.png");
  background-size: cover;
  float: right;
}
.desc3 h3,
.desc3 p {
  text-align: right;
  color: #353535;
  display: inline-block;
}

.dots {
  position: absolute;
  text-align: right;
}

.dot {
  border-radius: 50%;
  display: inline-block;
}
.dot:nth-of-type(1) {
  border: 3px solid #595959;
  width: 3px;
}

.dot:nth-of-type(2),
.dot:nth-of-type(3) {
  border: 3px solid #e2e2e4;
  width: 3px;
  margin-left: 7px;
}
</style>
