<template>
  <div> 
    <span v-for="(KEY) in photos" :key="KEY">
      <img
          @click="toSinglePhoto(KEY)"
          class="AllPhotos" 
          :src="'https://s3-ap-northeast-1.amazonaws.com/react.sprint/' + KEY" />
    </span>
  </div>
</template>

<script>
export default {
  name: "AllPhotos",
  props: {
    photos: Array,
    isAllphotos: Boolean,
    selectedPhotos: String
  }, 
  methods: {
    toSinglePhoto(key) {
      this.$emit('toSinglePhoto',key)
      //1.change selected Photos
      //2. currentView to single photo
    }
  }
}
</script>

<style>

.AllPhotos {
  width:300px;
  height: 300px;
}

.AllPhotos:hover {
  zoom:150%;
}



</style>

