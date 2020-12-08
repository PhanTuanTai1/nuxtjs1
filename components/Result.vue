<template>
  <div style="display:inline-block;margin:10px;cursor: pointer;" @click="showDetail()">      
   <img calleranswer="Multimedia" class="vs_sample_img rms_img" role="presentation" v-bind:alt="Name" v-bind:src="'https://storage.googleapis.com/visionapisearch/' + Image" data-bm="22">
   <div class="vs_sample_img_shadow">
      <div class="vs_sample_text">{{Name}}</div>
   </div>
  </div>
</template>

<script>

export default {
  props: {
    Screen: { 
      type: String,
      default: null,
    },
    Description: { 
      type: String,
      default: null,
    },
    Image: { 
      type: String,
      default: null,
    },
    OS: { 
      type: String,
      default: null,
    },
    Name: { 
      type: String,
      default: null,
    },
  },
  methods: {
    showDetail () { 
      return null 
    },
  },
}
</script>