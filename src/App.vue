<template>
  <div id="app">
    <div>
   </div>
    <navbar :currentView="currentView"  @buttonClicked="toAllPhotos"></navbar>
    <allphotos 
    v-if="isAllphotos"
    :photos="photos" 
    :isAllphotos="isAllphotos" 
    :selectedPhotos="selectedPhotos" 
    @toSinglePhoto="toSinglePhoto"
    ></allphotos>
    <singlephoto v-else 
    :photos="photos"
    :selectedPhotos="selectedPhotos" ></singlephoto>
  
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
    isAllphotos: true, 
    selectedPhotos: "",
    photos: [],
  }),
  methods: {
    toAllPhotos(value) {
      this.currentView = true;
      console.log("current",this.currentView)
    },
    toSinglePhoto(key) {
      this.isAllphotos = false;
      this.selectedPhotos = key;
      console.log("current",this.currentView)   
      console.log("key",key)  
    }
  },
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
