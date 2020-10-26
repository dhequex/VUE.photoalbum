<template>
  <div class="NavBar">
    <h1>HOME</h1>
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
    currentView: String,
    selectedPhotos: String,
    photos: Array 
    },
  methods: {
    toAllPhotos() {
      this.$emit('toAllPhotos')
    }
  }
} 
</script>

<style>
.NavBar{
  background-color: rgb(8, 228, 173);
  width: 100%;
  height: 300px;
}


</style>
