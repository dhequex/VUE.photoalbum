<template>
  <div class="NavBar">
    <h1>Vueing the Photos by Jose and Kenny</h1>
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

</style>
