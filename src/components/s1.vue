<template>
  <div class="s1" :style="{height:computedHeight}">
    <div class="s1-bg"></div>
    <div class="s1-img"></div>
    <div class="txt-wrapper" :style="{top:txtTop,left:txtLeft}">
      <h1 class="heading">MAGBASE</h1>
      <div class="descr">EMPOWER YOUR ECHO DOT, GOOGLE HOME MINI WITH FREEDOM</div>
      <button class="s1-btn" :style="btnSize">COMING SOON</button>
    </div>
    <dot :dot-style="styleObj" :bgcolor="'#fff'" :lncolor="'black'"/>
  </div>
</template>

<script>
import dot from '@/components/dot.vue';
export default {
  name: "s1",
  props:['s1-style'],
  data(){
    return {
      styleObj:this.s1Style,
      txtTopRatio:293/1280,
      txtLeftRatio:338/1280,
      btnRatio:107/1280
    }
  },
  components:{
    dot
  },
  computed:{
    computedHeight(){
      return this.styleObj.win_width*this.styleObj.widthRatio + 'px';
    },
    txtTop(){
      return this.txtTopRatio*this.styleObj.win_width + 'px';
    },
    txtLeft(){
      return this.txtLeftRatio*this.styleObj.win_width + 'px';
    },
    btnSize(){
      return {
        width:this.btnRatio*this.styleObj.win_width + 'px',
        height:(25/1280)*this.styleObj.win_width + 'px'
      }
    }
  },
  beforeCreate(){
    
  }
};
</script>

<style scoped>

.s1{
  width:100vw;
  display: flex;
  justify-content: center;
  position: relative;
}

.s1-bg{
  width:calc(100% - 108px);
  background:#353535;
  height: 100%;
}

.s1-img{
  position: absolute;
  background-image: url('../assets/ptkMagbase.png');
  background-size: 100%;
  width:100%;
  height:100%;
  background-origin: border-box;
  transform:translateY(-70px);
}

.txt-wrapper{
  position: absolute;
  
}

.heading{
  letter-spacing: 5px;
  font-weight: 740;
  color: #fff;
  position: relative;
  font-size: 23px;
  display: inline-block;
}

.heading::after{
  content: 'TM';
  position: absolute;
  right: -18px;
  font-size: 6px;
  top: -2px;
  letter-spacing: 3px;

}

.descr{
  margin-top: 25px;
  width: 240px;
  line-height: 20px;
  font-size: 9px;
  color: #fff;
  letter-spacing: 2.3px;
}

.s1-btn{
  margin-top: 38px;
  background:#fff;
  color:#353535;
  font-size: 8px;
  border:none;
  outline: none;
      font-weight: 900;
    letter-spacing: 2px;
}
</style>
