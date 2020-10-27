<template>
  <div> 
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
  max-height:1000px;
  width:auto;
}

</style>
