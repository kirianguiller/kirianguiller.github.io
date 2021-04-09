<template>
  <div class="main">
    <button @click="flipped = !flipped">{{ flipped }}</button>

    <div v-bind:class="flipped ? 'flip-container flipped' : 'flip-container'">
      <div class="flipper">
        <div class="front" v-on:click="flipped = true">
          <slot name="front"></slot>
        </div>
        <div class="back" v-on:click="flipped = false">
          <slot name="back"></slot>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "FlipCard",
  data: function() {
    return {
      flipped: false
    };
  }
};
</script>

<style scoped>
i.frontFlipBtn,
i.backFlipBtn {
  position: absolute;
  right: 20px;
  top: 20px;
  color: #ffffff;
  background-color: red;
}
i.backFlipBtn {
  -webkit-transform: rotateY(-180deg);
  -moz-transform: rotateY(-180deg);
  -o-transform: rotateY(-180deg);
  -ms-transform: rotateY(-180deg);
  transform: rotateY(-180deg);
}
.flip-container {
  -webkit-perspective: 1000px;
  -moz-perspective: 1000px;
  -o-perspective: 1000px;
  perspective: 1000px;
  width: 400px;
  height: 500px;
  background-color: blue;
}
/* .flip-container {
  min-height: 120px;
} */
.flipper {
  -moz-transform: perspective(1000px);
  -moz-transform-style: preserve-3d;
  position: relative;
  width: 100%;
  height: 100%;
  transition: transorm 0.6s;
  transform-style: preserve-3d;
}

.flipped {
  transform: rotateY(180deg);
}
.front,
.back {
  -webkit-backface-visibility: hidden;
  -moz-backface-visibility: hidden;
  -o-backface-visibility: hidden;
  backface-visibility: hidden;
  /* -webkit-transition: 0.6s;
  -webkit-transform-style: preserve-3d;
  -moz-transition: 0.6s;
  -moz-transform-style: preserve-3d;
  -o-transition: 0.6s;
  -o-transform-style: preserve-3d;
  -ms-transition: 0.6s;
  -ms-transform-style: preserve-3d;
  transition: 0.6s;
  transform-style: preserve-3d; */
  /* top: 0;
  left: 0; */
  position: absolute;
  width: 100%;
  height: 100%;
  background-color: red;
}
/* .back {
  -webkit-transform: rotateY(-180deg);
  -moz-transform: rotateY(-180deg);
  -o-transform: rotateY(-180deg);
  -ms-transform: rotateY(-180deg);
  transform: rotateY(-180deg);
}
.flip-container.flipped .back {
  -webkit-transform: rotateY(0deg);
  -moz-transform: rotateY(0deg);
  -o-transform: rotateY(0deg);
  -ms-transform: rotateY(0deg);
  transform: rotateY(0deg);
}
.flip-container.flipped .front {
  -webkit-transform: rotateY(180deg);
  -moz-transform: rotateY(180deg);
  -o-transform: rotateY(180deg);
  -ms-transform: rotateY(180deg);
  transform: rotateY(180deg);
}
.front {
  z-index: 2;
} */
</style>
