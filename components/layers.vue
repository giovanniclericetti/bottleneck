<template>
  <div class="layer-section pt-2 pb-0">
    <div class="pt-md-5 pt-0 p-md-0 p-4">
      <div class="d-flex justify-content-center">
        <h2 class="pt-5">Two layers to prevent useless notifications</h2>
      </div>
      <div class="d-flex justify-content-center">
        <p style="max-width: 700px">
          Bottleneck features two different dashboard layers. One immediately shown,
          to display the most important notifications. The other, reachable via the “go
          deeper” button, summarizes all the missed notifications, to keep you updated,
          without having you feel overwhelmed.
        </p>
      </div>
    </div>

    <div class="mt-5 pb-5">

      <div class="mt-5 pb-5">
        <div>
          <video autoplay muted loop class="videoloopcentered">
            <source src="video/doppiolayer.mp4" type="video/mp4">
          </video>
        </div>
      </div>

    </div>
  </div>
</template>

<script>
export default {
  name: "layers",
  mounted() {
    this.setupVideoScroll();
  },
  methods: {
    setupVideoScroll() {
      const videoElementLayers = this.$refs.videoElementLayers;
      let previousScrollTop = 0;
      let rafId = null;
      let videoVisible = false;

      const updateVideoFrame = () => {
        const scrollTop = window.pageYOffset || document.documentElement.scrollTop;
        const scrollDelta = scrollTop - previousScrollTop;

        if (!videoVisible && this.isElementInViewport(videoElementLayers)) {
          videoVisible = true;
          videoElementLayers.play();
        } else if (videoVisible && !this.isElementInViewport(videoElementLayers)) {
          videoElementLayers.pause();
        }

        if (videoVisible) {
          videoElementLayers.currentTime = videoElementLayers.currentTime + scrollDelta * 0.003;
        }

        previousScrollTop = scrollTop;
        rafId = requestAnimationFrame(updateVideoFrame);
      };

      const startVideoScroll = () => {
        if (!rafId) {
          rafId = requestAnimationFrame(updateVideoFrame);
        }
      };

      const stopVideoScroll = () => {
        cancelAnimationFrame(rafId);
        rafId = null;
      };

      window.addEventListener("scroll", startVideoScroll);
      window.addEventListener("resize", startVideoScroll);
      window.addEventListener("blur", stopVideoScroll);
      window.addEventListener("focus", startVideoScroll);
    },
    isElementInViewport(element) {
      const rect = element.getBoundingClientRect();
      return (
        rect.top >= 0 &&
        rect.left >= 0 &&
        rect.bottom <= (window.innerHeight || document.documentElement.clientHeight) &&
        rect.right <= (window.innerWidth || document.documentElement.clientWidth)
      );
    },
  },
  beforeDestroy() {
    window.removeEventListener("scroll", this.startVideoScroll);
    window.removeEventListener("resize", this.startVideoScroll);
    window.removeEventListener("blur", this.stopVideoScroll);
    window.removeEventListener("focus", this.startVideoScroll);
  }
};
</script>

<style scoped>

</style>
