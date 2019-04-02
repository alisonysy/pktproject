<template>
  <div class="about">
    <button class="upload-button button" type="button" @click="upload">Upload</button>
    <image-compressor :done="getFiles" :scale="scale" :quality="quality"></image-compressor>
    <div class="text-center" v-if="img">
      <img v-if="img" src="" alt="" :style="{ maxWidth: originalSize ? '100%' : null }" :src="img">
    </div>
  </div>
</template>

<script>
import imageCompressor from "vue-image-compressor";
export default {
  data() {
    return {
      img: "",
      scale: 100,
      quality: 50,
      originalSize: true,
      original: {},
      compressed: {}
    };
  },
  components: { imageCompressor },
  methods: {
    upload() {
      let compressor = this.$refs.compressor.$el;
      console.log(this.$refs.compressor);
      console.log(this.$refs.compressor.$el)
      compressor.click();
    },
    getFiles(obj) {
      console.log(obj);
      this.img = obj.compressed.blob;
      this.original = obj.original;
      this.compressed = obj.compressed;
    }
  }
};
</script>
