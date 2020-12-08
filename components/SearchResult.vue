<template>
    <div style="display:inline-block;margin:10px;cursor: pointer;">      
   <img calleranswer="Multimedia" class="vs_sample_img rms_img" role="presentation" v-bind:alt="Name" v-bind:src="Image" data-bm="22">
   <div class="vs_sample_img_shadow">
      <div class="vs_sample_text">{{Name}}</div>
   </div>
  </div>
</template>

<script>
export default {
  props: {
    Image: { 
      type: String,
      default: null,
      required: true
    },
    Description: { 
      type: String,
      default: null,
      required: true
    },
    Name: { 
      type: String,
      default: null,
      required: true
    },
  },
    
}
</script>