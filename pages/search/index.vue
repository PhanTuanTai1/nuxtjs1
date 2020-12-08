<template src='./index.html'></template>

<script>
import Result from "~/components/Result.vue";
import SearchResult from "~/components/SearchResult.vue";
import axios from "axios";
import vueDropzone from "vue2-dropzone";
import { QrcodeStream, QrcodeDropZone, QrcodeCapture } from 'vue-qrcode-reader'

export default {
  methods: {
    CallApi() {
      var keyword = document.getElementById("sbi_searchbox_input").value;

      axios
        .get("https://localhost:5001/search/SearchProductByKeyWord?keyword=" + keyword,{
            headers:{"Access-Control-Allow-Origin": "*"}
        })
        .then((res) => {
          this.lstVisualSearchProduct = null;
          this.lstProduct = res.data;
        });
    },
    UpdateStatus(file, response) {
      this.lstProduct = null;
      this.lstVisualSearchProduct = response;
    },
    showCamera(){
      this.showCameraCheck = true;
    },
    onDecode(decodedString){
      alert(decodedString);
      this.showCameraCheck = false;
    }
  },
  data() {
    return {
      lstProduct: [],
      lstVisualSearchProduct: [],
      showCameraCheck: false,
      dropOptions: {
        url: "https://localhost:5001/search/SearchByImage",
        maxFilesize: 2, // MB
        maxFiles: 4,
        sending: function(file, response){
            file.previewElement.innerHTML = "";
        }
      }
    };
  },
  components: {
    Result,
    vueDropzone,
    SearchResult,
    QrcodeStream,
    QrcodeDropZone,
    QrcodeCapture
  }
};
</script>

<style src='./style.css'>
</style>