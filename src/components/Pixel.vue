<template>
  <div :class="['pixel', color, current ? 'current' : '']" @click="handleClick"></div>
</template>

<style scoped>
.pixel {
  border: 1px solid lightgray;
  width: 30px;
  height: 30px;
  box-sizing: border-box;
}
.pixel.current {
  border: 4px solid yellow;
}
.white {
  background-color: white;
}
.lightgreen {
  background-color: rgb(108, 189, 100);
}
.green {
  background-color: rgb(0, 150, 0);
}
.darkgreen {
  background-color: rgb(29, 90, 20);
}
</style>

<script>
export default {
  name: "Pixel",
  props: {
    color: String,
    current: Boolean,
    isInColorPicker: Boolean,
    isInCanvas: Boolean,
    index: Number
  },
  methods: {
    handleClick: function() {
      if (this.isInColorPicker) {
        this.$root.$emit("updatecolor", this.color)
      }
      if (this.isInCanvas) {
        this.$root.$emit("clickedpixel", this.index)
      }
    }
  }
}
</script>