<template>
  <div>
    <Pixel isInColorPicker color="white" :current="color == 'white' ? true : false"/>
    <Pixel isInColorPicker color="lightgreen" :current="color == 'lightgreen' ? true : false"/>
    <Pixel isInColorPicker color="green" :current="color == 'green' ? true : false"/>
    <Pixel isInColorPicker color="darkgreen" :current="color == 'darkgreen' ? true : false"/>
  </div>
</template>

<script>
import Pixel from "./Pixel";

export default {
  name: "ColorPicker",
  props: {
    color: String
  },
  methods: {
    changeColor: function(color) {
      alert(color);
    }
  },
  components: {
    Pixel
  }
};
</script>

