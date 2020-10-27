<template>
  <div>
    <input class="input" ref="fileInput" @change="uploadFile" type="file"/>
    <button class="uploadButton" @click="clickInput()"  >UPLOAD</button>
  </div>
</template> 

<script>
import { saveObject }  from "../../utils/index.js"
export default {
  name: "Upload",
  methods: {
   uploadFile(event) {
     saveObject(event.target.files[0])
    },
   clickInput() {
      console.log("it workes")
      this.$refs.fileInput.click();
    }
  }
};
</script>

<style>
.input{
  display:none
}
</style>
