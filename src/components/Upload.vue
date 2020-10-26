<template>
  <div>
    <input @change="uploadFile" type="file"/>
    <button>UPLOAD</button>
  </div>
</template> 

<script>
import { listObjects, saveObject,getSingleObject }  from "../../utils/index.js"
export default {
  name: "Upload",
  methods: {
   uploadFile(event) {
     console.log("hi");
     saveObject(event.target.files[0])
    }
  }
};
</script>

<style></style>
