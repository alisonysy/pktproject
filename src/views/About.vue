<template>
  <div class="about">
    <image-compressor :done="getFiles" :scale="scale" :quality="quality"></image-compressor>
    
      <img src="blob:https://alisonysy.github.io/a1500723-b96a-419a-8fa4-9b1f0f742ce7" alt="" :style="{ maxWidth: originalSize ? '100%' : null }">
   
  </div>
</template>

<script>
import imageCompressor from "vue-image-compressor";
export default {
  data() {
    return {
      img: "",
      scale: 100,
      quality: 90,
      originalSize: true,
      original: {},
      compressed: {}
    };
  },
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
