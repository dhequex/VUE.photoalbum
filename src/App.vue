<template>
  <div id="app">
    <div>
   </div>
    <navbar :currentView="currentView"  @toAllPhotos="currentView = AllPhotos"></navbar>
    <allphotos :photos="photos" v-if="currentview === AllPhotos"></allphotos>
    <singlephoto :photos="photos"  v-else></singlephoto>
  
  </div>
</template>



<script>
import Navbar from "./components/Navbar";
import AllPhotos from "./components/AllPhotos";
import SinglePhoto from "./components/SinglePhoto";
import { listObjects, saveObject }  from "../utils"


export default {
  name: "App",
  components: {
    navbar: Navbar,
    allphotos: AllPhotos,
    singlephoto: SinglePhoto
  },
  data: () => ({
    title: "CC Photo Library",
    currentView: "AllPhotos", 
    selectedPhotos: "selected",
    photos: [],
  }),
  created: async function () {
    console.log("created called");
    let photoArr = await listObjects();
    photoArr= photoArr.map(x=>x.Key)
                      .filter(x=> !x.includes(".mov") && !x.includes(".HEIC"))
    this.photos=photoArr;  
  }
}

</script>

<style>
.NavBar{
  background-color: #42B6A4;
  width: 100%;
  height: 300px;
}
</style>
