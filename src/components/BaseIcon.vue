<template>
  <div class="icon-wrapper">
    <svg
      class="icon"
      :width="width"
      :height="height"
      :style="styleObject"
      :class="activeHover ? 'active-hover' : ''"
    >
      <use v-bind="{ 'xlink:href': '/feather-sprite.svg#' + name }" />
    </svg>
  </div>
</template>

<script>
export default {
  props: {
    name: String,
    width: {
      type: [Number, String],
      default: 24
    },
    height: {
      type: [Number, String],
      default: 24
    },
    color: {
      type: String,
      default: "white"
    },
    activeHover: {
      type: Boolean,
      default: true
    },
    colorHover: {
      type: String,
      default: "blue"
    }
  },
  computed: {
    styleObject: function() {
      return {
        "--color": this.color,
        "--color-hover": this.colorHover
      };
    }
  }
};
</script>

<style scoped>
.icon-wrapper {
  display: inline-flex;
  align-items: center;
  color: rgba(0, 0, 0, 0.4);
  font-size: 1rem;
  font-weight: 600;
}
.icon {
  stroke: currentColor;
  stroke-width: 2;
  stroke-linecap: round;
  stroke-linejoin: round;
  fill: none;
  color: var(--color);
  /* margin-right: 6px; */
}

.active-hover:hover {
  color: var(--color-hover);
}
</style>
