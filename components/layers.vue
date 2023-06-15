<template>
  <div class="layer-section pt-2 pb-0">
    <div class="textbox pt-md-5 pt-5 p-md-0 p-4">
      <h2 class="pt-5">Two layers to prevent useless notifications</h2>
      <div class="d-flex justify-content-center">
        <p style="max-width: 700px">
          Bottleneck features two different dashboard layers. One immediately shown,
          to display the most important notifications. The other, reachable via the “go
          deeper” button, summarises all the missed notifications, to keep you updated,
          without having you feel overwhelmt.
        </p>
      </div>
    </div>

    <div class="my-5 pb-5">
      <div>
        <video ref="videoElementLayers" class="videoscroll" >
          <source src="https://www.w3schools.com/html/mov_bbb.mp4" type="video/mp4">
        </video>
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
          const newFrame = videoElementLayers.currentTime + scrollDelta * 0.01;
          videoElementLayers.currentTime = newFrame;
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
}
</script>

<style scoped>

.layer-section {
  background-color: #DFEAEA;
  width: 100%;
  margin: 0px;
}

h2 {
  font-size: 48px;
  font-family: mondwest;
}

p {
  font-size: 18px;
}

.textbox {
  color: #25454D;
}

.videoscroll{
  width: 60%
}

@media (max-width: 768px) {

  h2 {
    font-size: 32px;
    font-family: mondwest;
  }

  .videoscroll{
    width: 90%
  }

}

</style>
