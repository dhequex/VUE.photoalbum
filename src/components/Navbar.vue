<template>
  <div>
    <h1>{{title}}</h1>
    
  </div>
</template>

<script>



export default {
  name: "Navbar",
  props: {
    title: String,
    currentView: String,
    selectedPhotos: String,
    photos: Array 
    }
};
</script>

<style></style>

