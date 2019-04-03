<template>
  <div id="app" @click="clicked">
        <s1 :s1-style="styleObj"/>
        <s2 :s2-style="styleObj"/>
        <s3 :s3-style="styleObj"/>
        <s4 :s4-style="styleObj"/>
  </div>
</template>

<script>
import s1 from '@/components/s1.vue';
import s2 from '@/components/s2.vue';
import s3 from '@/components/s3.vue';
import s4 from '@/components/s4.vue';
export default {
  data(){
    return {
      styleObj:{
        win_width:'',
        widthRatio:810/1280
      }
    }
  },
  components:{
    s1,
    s2,
    s3,
    s4
  },
  methods:{
    clicked(e){
      console.log(e.pageX + ' '+ e.pageY)
    }
  },
  created(){
    this.styleObj.win_width = document.documentElement.clientWidth;
  }
}
</script>


<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  width:100vw;
}

*{
  box-sizing: border-box;
  margin:0;
  padding:0;
}

</style>
