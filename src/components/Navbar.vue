<template>
  <div class="NavBar">
    <h1 class="Topic">Vueing the Photos by Jose and Kenny</h1>
    <img class="logo" src="https://pbs.twimg.com/profile_images/1281073106711310337/lJkvgoyy_400x400.png" />
    <button @click="toAllPhotos()">Show All Photos</button>
    <upload/>
  </div>
</template>

<script>
import Upload from "./Upload";

export default {
  name: "Navbar",
  components: {
    upload:Upload,
  },
  props: {
    title: String,
    isAllphotos: Boolean,
    selectedPhotos: String,
    photos: Array 
    },
  methods: {
    toAllPhotos() {
      this.$emit('buttonClicked')
    }
  }
} 
</script>

<style>

.logo{
  max-height:100px;
  margin-bottom:auto;
  margin-left: auto;
}
.Topic {
  font-size:60px;
  text-align: center;
  margin-top:10px;
}
</style>
