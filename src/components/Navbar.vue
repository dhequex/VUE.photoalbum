<template>
  <div class="NavBar">
    <h1 class="Topic">CC15 Vue Library</h1>
    <h3 class="SubTopic"> By Jose and Kenny</h3>
    <span class="nav-row"> 
    <button class="allButton" @click="toAllPhotos()">Show All Photos</button>
    <img class="logo" src="https://pbs.twimg.com/profile_images/1281073106711310337/lJkvgoyy_400x400.png" />
    <upload/>
    </span>
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
.NavBar{
  background-color: #42B6A4;
  width: 100%;
  height: 400px;
}



.Topic {
  font-family: 'Raleway', sans-serif;
  font-size:60px;
  text-align: center;
  margin-top:10px;
  color: rgb(255, 255, 255);
}



.uploadButton{
  position:absolute;
  left:20%;
  height:50px;
  font-size:20px;
  margin-bottom:auto;
  margin-left: 50%;
}

.logo{
  max-height:100px;
  margin-bottom:auto;
  margin-left: 48%;
}

.allButton{
  position:absolute;
  top:24%;
  left:25%;
  height:50px;
  font-size:20px;
  margin-bottom:auto;
  margin-left: auto;
}

.SubTopic {
  font-family: 'Raleway', sans-serif;
  font-size:20px;
  text-align: center;
  margin-top:10px;
  color: rgb(255, 255, 255);
}





</style>
