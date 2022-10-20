<script type="module">
import { AdvancedImage } from "@cloudinary/vue3"
import {Cloudinary} from "@cloudinary/url-gen";
import {fill} from "@cloudinary/url-gen/actions/resize";

// Create a Cloudinary instance and set your cloud name.
const cld = new Cloudinary({
    cloud: {
      cloudName: 'demo'
    }
  });

// Instantiate a CloudinaryImage object for the image with the public ID, 'docs/models'.
const myImg = cld.image('docs/models'); 

// Resize to 250 x 250 pixels using the 'fill' crop mode.
myImg.resize(fill().width(250).height(250));


export default {
  components: {
    AdvancedImage
  },
  data() {
    return {
      myImage: myImg
    };
  }
};
</script>

<template>
  <div class="App-body">
    <h1>Vue 3 Quick Start</h1>
    <AdvancedImage :cldImg="myImage"/>
  </div>
</template>