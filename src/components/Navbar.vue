<template>
  <div class="fixed-header cursive-font">
    <nav @click.prevent="clickHandle">
      <a href="header" id="landing">Welcome</a>
      <a href="experience">Experience</a>
      <a href="languages">Languages</a>
      <a href="it-skills">IT Skills</a>
      <a href="other">Other</a>
    </nav>
  </div>
</template>

<script>
export default {
  data() {
    return {
      activeAnchor: null,
      targetElements: [],
      closestTargetElement: null
    };
  },
  mounted() {
    this.activeAnchor = document.getElementById("landing");
    // this.activeAnchor.classList.add('active')
  },
  created() {
    setTimeout(this.updateCheckpointsCoordonates, 1000);
    window.addEventListener("resize", this.updateCheckpointsCoordonates);
    window.addEventListener("scroll", this.handleScroll);
  },
  watch: {
    activeAnchor(newValue, oldValue) {
      if (oldValue) {
        oldValue.classList.remove("active");
      }
      newValue.classList.add("active");
    }
  },
  methods: {
    clickHandle: function(e) {
      if (e.target.tagName === "A") {
        // this.activeAnchor = e.target;
        let toScrollId = e.target.getAttribute("href");
        if (toScrollId == "header") {
          window.scrollTo(0, 0);
        } else {
          let toScrollEl = document.getElementById(toScrollId);
          window.scrollTo(0, toScrollEl.offsetTop);
        }
      }
    },
    updateCheckpointsCoordonates: function() {
      let navAnchors = document.querySelectorAll("nav a");
      for (const navAnchor of navAnchors) {
        let toScrollId = navAnchor.getAttribute("href");
        this.targetElements.push(document.getElementById(toScrollId));
      }
    },
    // this function check which section (element) is at the top of the current scrolling
    handleScroll: function(e) {
      const scrollTop = e.target.scrollingElement.scrollTop;
      let closestTargetElement;
      for (const targetElement of this.targetElements) {
        if (scrollTop > targetElement.offsetTop - 20) {
          closestTargetElement = targetElement;
        } else {
          if (this.closestTargetElement != closestTargetElement) {
            this.closestTargetElement = closestTargetElement;
            this.activeAnchor = document.querySelector(
              `nav a[href=${closestTargetElement.getAttribute("id")}]`
            );
          }
          break;
        }
      }
    }
  }
};
</script>

<style scoped>
.fixed-header {
  position: fixed;
  left: 0px;
  top: 0px;
  width: 100%;
  height: 60px;
  z-index: 100;
  box-shadow: 0 1px 6px 0 rgba(32, 33, 36, 0.28);

  display: flex;
  align-items: center;
  justify-content: center;
}

a {
  padding: 12px;
  text-decoration: none;
  color: var(--color-dark);
}

a:not(.active) {
  color: var(--color-light);
}
</style>
