<template>
  <div class="experience-card">
    <grid-item-img>
      <!-- <div class="img-container"><img :src="src" /></div> -->
      <img v-if="src" :src="src" />
    </grid-item-img>
    <grid-item-content>
      <div class="text-container">
        <h3 class="main"><slot name="title"></slot></h3>
        <h4 class="light-accent">
          <slot name="detail"></slot>, <i><slot name="date"></slot></i>
        </h4>
        <h5 class="dark"><slot name="place"></slot></h5>
        <p class="description">
          <slot name="description"></slot>
        </p>
      </div>
    </grid-item-content>
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
  text-align: left;
}

.experience-card {
  margin: 40px 0;
  display: grid;
  grid-template-columns: [col1-start] 30% [col1-end col2-start] auto [col2-end];
  grid-gap: 50px;
  width: 80%;
  /* display: flex; */
  /* flex-direction: row; */
  /* flex-wrap: wrap; */
  /* justify-content: center; */
  /* align-items: center; */
}

grid-item-img {
  grid-column-start: col1-start;
  grid-column-end: col1-end;
  /* display: flex;
  justify-content: center;
  align-items: center; */
}

grid-item-content {
  grid-column-start: col2-start;
  grid-column-end: col2-end;
}

img {
  --img-width: 200;
  width: calc(var(--img-width) * 1px);
  height: calc(var(--img-width) / 100 * 70px);
  background-color: white;
  border-radius: 15px;
  -webkit-box-shadow: 0px 0px 8px 5px rgba(0, 0, 0, 0.28);
  -moz-box-shadow: 0px 0px 8px 5px rgba(0, 0, 0, 0.28);
  box-shadow: 0px 0px 8px 5px rgba(0, 0, 0, 0.28);
}

@media (max-width: 700px) {
  .experience-card {
    grid-template-rows: [row1-start] auto [row1-end row2-start] auto [row2-end];
    grid-template-columns: 1fr;
    grid-gap: 0;
    grid-row-gap: 30px;
  }

  grid-item-img {
    grid-row-start: row1-start;
    grid-row-end: row1-end;
  }

  grid-item-content {
    grid-row-start: row2-start;
    grid-row-end: row2-end;
  }
}

h5 {
  font-weight: 800;
}
</style>
