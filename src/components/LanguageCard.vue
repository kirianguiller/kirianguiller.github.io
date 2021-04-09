<template>
  <FlipCard>
    <template slot="front">
      <h3><slot name="front-title"></slot></h3>
      <p><slot name="front-text"></slot></p>
    </template>
    <template slot="back">
      <h3><slot name="back-title"></slot></h3>
      <p><slot name="back-text"></slot></p>
    </template>
  </FlipCard>
</template>

<script>
import FlipCard from "@/components/FlipCard.vue";
export default {
  components: {
    FlipCard
  }
};
</script>

<style scoped>
h3 {
  margin-top: 1rem;
}
p {
  margin: 1rem;
}
</style>
