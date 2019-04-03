<template>
  <div class="s5" :style="{height:computedHeight}">
    <div class="s5-img" :style="{backgroundPositionY:imgTrans}"></div>
    <h1 class="heading" :style="heading">COMPLETELY WIRELESSLY!</h1>
    <div class="expla-1" :style="explaOne">
      <h3 :style="explaOneTxt">TRANSMITTER COIL</h3>
      <div class="line" :style="explaLine">
        <div class="slope" :style="explaSlope"></div>
      </div>
    </div>
    <div class="expla-2" :style="explaTwo">
      <h3 :style="explaOneTxt">RECEIVER COIL</h3>
      <div class="line" :style="explaLine2">
        <div class="slope" :style="explaSlope2"></div>
      </div>
    </div>
    <div class="txt" :style="txt">
      BUILT IN BOTH THE TRANSMITTER COIL AND RECEIVER COIL, IT WIRELESS CHARGES<br>
      YOUR DEVICES, AND IT CAN BE WIRELESS CHARGED!
    </div>
            <dot :dot-style="styleObj" :bgcolor="'#000'" :lncolor="'white'"/>

  </div>
</template>

<script>
import dot from "@/components/dot.vue";

export default {
  name: "s5",
  props: ["s5-style"],
  components: {
    dot
  },
  data() {
    return {
      styleObj: this.s5Style
    };
  },
  computed: {
    computedHeight() {
      return (888 / 1280) * this.styleObj.win_width + "px";
    },
    imgTrans() {
      return "-" + (3530 / 1280) * this.styleObj.win_width + "px";
    },
    heading() {
      return {
        top: (125 / 1280) * this.styleObj.win_width + "px",
        fontSize: (18 / 1280) * this.styleObj.win_width + "px",
        letterSpacing: (3 / 1280) * this.styleObj.win_width + "px"
      };
    },
    explaOne() {
      return {
        top: (260 / 1280) * this.styleObj.win_width + "px",
        left: (243 / 1280) * this.styleObj.win_width + "px"
      };
    },
    explaOneTxt() {
      return {
        fontSize: (8 / 1280) * this.styleObj.win_width + "px"
      };
    },
    explaLine() {
      return {
        width: (48 / 1280) * this.styleObj.win_width + "px",
        top: (16 / 1280) * this.styleObj.win_width + "px",
        right:0
      };
    },
    explaSlope() {
      return {
        width: (220 / 1280) * this.styleObj.win_width + "px",
        top:(90/1280)* this.styleObj.win_width + "px",
        left:(5/1280)* this.styleObj.win_width + "px"
      };
    },
    explaTwo(){
      return {
        top:(190/1280)* this.styleObj.win_width + "px",
        right:(220/1280)* this.styleObj.win_width + "px",
      }
    },
    explaLine2() {
      return {
        width: (155 / 1280) * this.styleObj.win_width + "px",
        top: (16 / 1280) * this.styleObj.win_width + "px",
        
      };
    },
    explaSlope2(){
      return {
        width:(280/1280)* this.styleObj.win_width + "px",
        top:(105/1280)* this.styleObj.win_width + "px",
        right:(105/1280)*this.styleObj.win_width + "px",
      }
    },
    txt() {
      return {
        width: (645 / 1280) * this.styleObj.win_width + "px",
        fontSize: (10/1280)*this.styleObj.win_width + "px",
        bottom:(110/1280)*this.styleObj.win_width +'px',
        lineHeight:(22/1280)*this.styleObj.win_width+'px',
        letterSpacing:(3/1280)*this.styleObj.win_width+'px',
      };
    }
  }
};
</script>

<style scoped>
.s5 {
  width: 100vw;
  display: flex;
  justify-content: center;
  position: relative;
}

.s5-img {
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

.expla-1 {
  position: absolute;
}

.expla-1 h3 {
  letter-spacing: 2px;
  font-weight: bolder;
  color:#353535;
}

.line {
  position: absolute;
  border-top: 1px dotted #eee;
}

.expla-1 .slope {
  position: absolute;
  border-top: 1px dotted #eee;
  transform: rotate(55deg);
}

.expla-2 {
  position: absolute;
}
.expla-2 h3 {
  letter-spacing: 2px;
  font-weight: bolder;
  color:#353535;
}


.expla-2 .line{
  right:50%;
  
}
.expla-2 .slope {
  position: absolute;
  border-top: 1px dotted #eee;
  transform: rotate(130deg);
}

.txt {
  position: absolute;
  font-weight: bold;
  text-align: center;
  color:#353535;
}
</style>
