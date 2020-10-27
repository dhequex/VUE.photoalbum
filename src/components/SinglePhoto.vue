<template>
  <div class="singleDiv"> 
      <img
          class="SinglePhoto" 
          :src="'https://s3-ap-northeast-1.amazonaws.com/react.sprint/' + selectedPhotos" />
  </div>
</template>

<script>
export default {
  name: "SinglePhoto",
  props: {
    photos: Array,
    selectedPhotos: String
  }, 
};
</script>

<style>
.SinglePhoto{
  max-height:600px;
  width:auto;
  position: absolute;
  top: 40%;
  left: 37%;
}


</style>
