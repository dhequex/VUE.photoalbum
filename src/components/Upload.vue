<template>
  <div>
    <input ref="fileInput" @change="uploadFile" type="file"/>
    <button @click="clickInput()"  >UPLOAD</button>
  </div>
</template> 

<script>
import { listObjects, saveObject,getSingleObject }  from "../../utils/index.js"
export default {
  name: "Upload",
  methods: {
   uploadFile(event) {
     saveObject(event.target.files[0])
    },
   clickInput() {
      console.log("it workes")
    }
  }
};
</script>

<style></style>
