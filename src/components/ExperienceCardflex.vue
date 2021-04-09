<template>
  <div class="experience-card">
    <div class="flex-container">
      <div class="flex-item img">
        <img v-if="src" :src="src" />
      </div>
      <div class="flex-item header">
        <h3 class="main"><slot name="title"></slot></h3>
        <h4 class="light-accent">
          <slot name="detail"></slot>, <i><slot name="date"></slot></i>
        </h4>
        <h5 class="dark"><slot name="place"></slot></h5>
      </div>
    </div>
    <div class="text">
      <p class="description">
        <slot name="description"></slot>
      </p>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    src: {
      type: String,
      default: ""
    }
  }
};
</script>

<style scoped>
* {
  font-family: "Roboto", "Helvetica", "Arial", sans-serif;
  text-align: left;
}

.experience-card {
  margin: 50px 10%;
}

.flex-container {
  display: flex;
  flex-flow: row nowrap;
  justify-content: space-between;
}

.flex-item.img {
  order: 2;
}

.flex-item.header {
  order: 1;
}

img {
  --img-width: 200;
  width: calc(var(--img-width) * 1px);
  height: auto;
  background-color: white;
  border-radius: 15px;
  -webkit-box-shadow: 0px 0px 8px 5px rgba(0, 0, 0, 0.28);
  -moz-box-shadow: 0px 0px 8px 5px rgba(0, 0, 0, 0.28);
  box-shadow: 0px 0px 8px 5px rgba(0, 0, 0, 0.28);
}

@media (max-width: 700px) {
  .flex-container {
    display: flex;
    flex-flow: column;
    justify-content: default;
  }

  .flex-item.header {
    order: 2;
  }

  img {
    width: 80%;
    height: auto;
  }

  .img {
    text-align: center;
    display: block;
  }
}
h5 {
  font-weight: 800;
}
</style>
