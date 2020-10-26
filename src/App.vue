<template>
  <div id="app">
    <div>
   </div>
    <img alt="Vue logo" src="./assets/logo.png" />
    <h1>{{ title }}</h1>
    <h2>{{currentView}}</h2>
    <navbar :title="title"></navbar>
  </div>
</template>

<script>
import Navbar from "./components/Navbar";
import AllPhotos from "./components/AllPhotos";
import SinglePhoto from "./components/SinglePhoto";



export default {
  name: "App",
  components: {
    navbar: Navbar,
    AllPhotos: AllPhotos,
    SinglePhoto: SinglePhoto
  },
  
  data: () => ({
    title: "Photo Upload App",
    currentView: "All Photos", 
    selectedPhotos: "selected",
    photos: [ 1, 2, 3],
  })
};
</script>

<style>
#app {
  text-align: center;
}
</style>
