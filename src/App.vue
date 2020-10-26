<template>
  <div id="app">
    <div>
   </div>
    <img alt="Vue logo" src="./assets/logo.png" />
    <h1>{{ title }}</h1>
    <h2>{{currentView}}</h2>
    <navbar :title="title"></navbar>
    <allphotos :photos="photos" v-if="currentview === AllPhotos"></allphotos>
    <singlephoto v-else></singlephoto>
  
  </div>
</template>



<script>
import Navbar from "./components/Navbar";
import AllPhotos from "./components/AllPhotos";
import SinglePhoto from "./components/SinglePhoto";
import { listObjects, saveObject,getSingleObject }  from "../utils/"


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
                      .filter(x=> )
    this.photos=photoArr;
    console.log(photoArr);
  
  }
}

</script>

