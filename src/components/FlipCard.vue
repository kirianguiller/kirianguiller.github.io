<template>
  <div class="flip-card-container">
    <div class="flip-card" :class="flipped ? 'flipped' : ''">
      <div class="flip-card-front bg-dark">
        <div @click="flipped = true">
          <BaseIcon
            name="arrow-left-circle"
            color="white"
            colorHover="#39b982"
            :height="32"
            :width="32"
            class="icon"
          />
        </div>
        <slot name="front"></slot>
      </div>
      <div class="flip-card-back bg-main dark">
        <div class="icon" @click="flipped = false">
          <BaseIcon
            name="arrow-right-circle"
            color="black"
            colorHover="#fff"
            :height="32"
            :width="32"
          />
        </div>
        <slot name="back"></slot>
      </div>
    </div>
  </div>
</template>

<script>
import BaseIcon from "@/components/BaseIcon.vue";

export default {
  components: {
    BaseIcon
  },
  name: "FlipCard",
  data: function() {
    return {
      flipped: true
    };
  }
};
</script>

<style scoped>
/* * {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
} */
/* body {
  font-family: Arial, Helvetica, sans-serif;
  width: 100vw;
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
} */
.flip-card-container {
  max-width: 600px;
  height: 400px;
  -webkit-perspective: 1000px;
  -moz-perspective: 1000px;
  -o-perspective: 1000px;
  perspective: 1000px;
}
.flip-card {
  position: relative;
  width: 100%;
  height: 100%;
  transition: transform 1s;
  transform-style: preserve-3d;
}
.flipped {
  -webkit-transform: rotateY(-180deg);
  -moz-transform: rotateY(-180deg);
  -o-transform: rotateY(-180deg);
  -ms-transform: rotateY(-180deg);
  transform: rotateY(-180deg);
}

/* .flip-card-container:hover .flip-card {
  transform: rotateY(180deg); 
} */

/* Position the front and back side */
.flip-card-front,
.flip-card-back {
  position: absolute;
  width: 100%;
  height: 100%;
  backface-visibility: hidden;
  /* display: flex;
  justify-content: center;
  align-items: center; */
  border-radius: 2rem;
}
.flip-card-front {
  color: #fff;
}
.flip-card-back {
  color: #000;
  transform: rotateY(-180deg);
}

.icon:hover {
  cursor: pointer;
}

/* .icon {
  transform: rotateY(180deg);
} */

.flip-card-front .icon {
  position: absolute;
  top: 20px;
  right: 20px;
}

.flip-card-back .icon {
  position: absolute;
  top: 20px;
  right: 20px;
}
</style>
