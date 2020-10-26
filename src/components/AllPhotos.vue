<template>
  <div> 
    <h1>I am All photos!</h1>
    <p> In all photos: {{photos}}</p>

  </div>
</template>

<script>
export default {
  name: "AllPhotos",
  props: {
    photos: Array
  }
};
</script>

<style></style>
