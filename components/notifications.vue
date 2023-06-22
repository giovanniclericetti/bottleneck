<template>
  <div class="notification-section pt-2 pb-0 m-0">
    <div class="text-white pt-md-5 pt-0 p-md-0 p-4">
      <div class="d-flex justify-content-center">
        <h2 class="pt-5 text-white">We feel you: too many notifications, right?</h2>
      </div>
      <div class="d-flex justify-content-center">
        <p style="max-width: 600px" class="text-white">
          We do know how it feels to be overwhelmed by notifications. You try to
          block them and just end up with losing precious and urgent
          information.... or try to keep it up losing concentration and
          deteriorating your mental health.
        </p>
      </div>
    </div>

    <div class="mt-5 p-0">
      <div class="d-none d-md-block" style="background-color: white">
        <video ref="videoElement" class="videoscroll">
          <source src="video/notifications.mp4" type="video/mp4">
        </video>
      </div>

      <div class="d-flex d-md-none imgmobile justify-content-center">
        <img src="~assets/img/notifications-static.png" alt="notifications">
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "notifications",
  mounted() {
    this.setupVideoScroll();
  },
  methods: {
    setupVideoScroll() {
      const videoElement = this.$refs.videoElement;
      let previousScrollTop = 0;
      let rafId = null;
      let videoVisible = false;

      const updateVideoFrame = () => {
        const scrollTop = window.pageYOffset || document.documentElement.scrollTop;
        const scrollDelta = scrollTop - previousScrollTop;

        if (!videoVisible && this.isElementInViewport(videoElement)) {
          videoVisible = true;
          videoElement.play();
        } else if (videoVisible && !this.isElementInViewport(videoElement)) {
          videoElement.pause();
        }

        if (videoVisible) {
          videoElement.currentTime = videoElement.currentTime + scrollDelta * 0.002;
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
