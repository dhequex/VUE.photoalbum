<template>
  <div id="app">
    <navbar :currentView="currentView"  @buttonClicked="toAllPhotos"></navbar>
    <img class="loading" src="https://flevix.com/wp-content/uploads/2019/07/Bar-Preloader-1.gif" v-if="photos.length===0"/>
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
      this.isAllphotos = true;
      console.log("isAllphotos",this.currentView)
    },
    toSinglePhoto(key) {
      this.isAllphotos = false;
      this.selectedPhotos = key;
      console.log("isAllphotos",this.currentView)   
      console.log("key",key)  ;
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


#app{
  width:100vw;
  height:80vh;
}

.loading{
  margin-left:30%
}
</style>
