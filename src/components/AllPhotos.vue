<template>
  <div> 
    <h1>I am All photos!</h1>
    <div v-for="(KEY, index) in photos" :key="index">
      <img :src="'https://s3-ap-northeast-1.amazonaws.com/react.sprint/' + KEY" />
    </div>
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


  <img v-for="(KEY, index) in photos" :key="index">
  src={`https://s3-ap-northeast-1.amazonaws.com/react.sprint/${KEY}`}
  </img>

  <img v-for="image in images" :src="image.url" :alt="image.alt" />

src="'https://s3-ap-northeast-1.amazonaws.com/react.sprint/' + 'KEY'"
   // 