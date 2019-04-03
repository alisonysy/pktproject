<template>
  <div class="s1" :style="{height:computedHeight}">
    <div class="s1-bg"></div>
    <div class="s1-img"></div>
    <div class="txt-wrapper" :style="{top:txtTop,left:txtLeft}">
      <h1 class="heading" :style="heading">MAGBASE</h1>
      <div class="descr" :style="desc">EMPOWER YOUR ECHO DOT, GOOGLE HOME MINI WITH FREEDOM</div>
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
        height:(25/1280)*this.styleObj.win_width + 'px',
        fontSize:(8/1280)*this.styleObj.win_width + 'px',
      }
    },
    desc(){
      return {
  marginTop: (25/1280)*this.styleObj.win_width + 'px',
  width: (240/1280)*this.styleObj.win_width + 'px',
  lineHeight: (20/1280)*this.styleObj.win_width + 'px',
  fontSize: (9/1280)*this.styleObj.win_width + 'px',
  letterSpacing:(2.3/1280)*this.styleObj.win_width + 'px',
      }
    },
    heading(){
    return {
        letterSpacing: (5/1280)*this.styleObj.win_width + 'px',
        fontSize:(23/1280)*this.styleObj.win_width + 'px',
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
  font-weight: 740;
  color: #fff;
  position: relative;
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

  color: #fff;

}

.s1-btn{
  margin-top: 38px;
  background:#fff;
  color:#353535;
  border:none;
  outline: none;
      font-weight: 900;
    letter-spacing: 2px;
    cursor:pointer;
}

.s1-btn:hover{
  background:#f5f6f8;
  box-shadow: 1px 1px 3px 2px rgba(0,0,0,0.55)
}
</style>
