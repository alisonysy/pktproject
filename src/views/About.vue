<template>
  <div class="about">
    <image-compressor :done="getFiles" :scale="scale" :quality="quality"></image-compressor>
    
      <img v-if="img" src="" alt="" :style="{ maxWidth: originalSize ? '100%' : null }" :src="img">
   
  </div>
</template>

<script>
import imageCompressor from "vue-image-compressor";
export default {
  /*data() {
    return {
      img: "",
      scale: 100,
      quality: 50,
      originalSize: true,
      original: {},
      compressed: {}
    };
  },*/
  components: { imageCompressor },
  methods: {
    getFiles(obj) {
      console.log(obj);
      /*this.img = obj.compressed.blob;
      this.original = obj.original;
      this.compressed = obj.compressed;*/
    }
  }
};
</script>
