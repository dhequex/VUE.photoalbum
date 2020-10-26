<template>
  <div> 
    <h1>I am All photos!</h1>
    <span v-for="(KEY, index) in photos" :key="index">
      <img class="AllPhotos" :src="'https://s3-ap-northeast-1.amazonaws.com/react.sprint/' + KEY" />
    </span>
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

<style>

.AllPhotos {
  width:300px;
  height: 300px;
}



</style>

