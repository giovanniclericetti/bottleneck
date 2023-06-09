<template>
  <div class="notification-section pt-2">
    <div class="textbox pt-5">
      <h2 class="pt-5">We feel you: too many notifications, right?</h2>
      <div class="d-flex justify-content-center">
        <p style="max-width: 600px">
          We do know how it feels to be overwhelmed by notifications. You try to
          block them and just end up with losing precious and urgent
          informations.... or try to keep it up losing concentration and
          deteriorating your mental health.
        </p>
      </div>
    </div>

    <div class="mt-5" >
      <img class="d-md-none" style="width: 80%" src="~assets/img/notifications.png" />

      <div class="d-md-block d-none">


        <video
          class="video"
          id="videoplay"
          playsinline="true"
          webkit-playsinline="true"
          preload="auto"
          muted="muted"
            src="~assets/video/notificationvideo.mp4"
            type="video/mp4"
          />

        <video

          src="~assets/video/notifications.mp4"

        />


      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "notifications",
  mounted() {
    const scriptUrls = [
      "https://cdnjs.cloudflare.com/ajax/libs/gsap/3.5.1/gsap.min.js",
      "https://cdnjs.cloudflare.com/ajax/libs/gsap/3.5.1/CSSRulePlugin.min.js",
      "https://s3-us-west-2.amazonaws.com/s.cdpn.io/16327/CustomBounce3.min.js",
      "https://s3-us-west-2.amazonaws.com/s.cdpn.io/16327/CustomEase3.min.js",
      "https://s3-us-west-2.amazonaws.com/s.cdpn.io/16327/CustomWiggle3.min.js",
      "https://s3-us-west-2.amazonaws.com/s.cdpn.io/16327/DrawSVGPlugin3.min.js",

      "https://cdnjs.cloudflare.com/ajax/libs/gsap/3.5.1/EaselPlugin.min.js",
      "https://cdnjs.cloudflare.com/ajax/libs/gsap/3.5.1/EasePack.min.js",
      "https://s3-us-west-2.amazonaws.com/s.cdpn.io/16327/GSDevTools3.min.js",
      "https://s3-us-west-2.amazonaws.com/s.cdpn.io/16327/InertiaPlugin.min.js",
      "https://s3-us-west-2.amazonaws.com/s.cdpn.io/16327/MorphSVGPlugin3.min.js",
      "https://s3-us-west-2.amazonaws.com/s.cdpn.io/16327/MotionPathHelper.min.js",
      "https://cdnjs.cloudflare.com/ajax/libs/gsap/3.5.1/MotionPathPlugin.min.js",
      "https://s3-us-west-2.amazonaws.com/s.cdpn.io/16327/Physics2DPlugin3.min.js",
      "https://s3-us-west-2.amazonaws.com/s.cdpn.io/16327/PhysicsPropsPlugin3.min.js",
      "https://cdnjs.cloudflare.com/ajax/libs/gsap/3.5.1/PixiPlugin.min.js",
      "https://s3-us-west-2.amazonaws.com/s.cdpn.io/16327/ScrambleTextPlugin3.min.js",
      "https://cdnjs.cloudflare.com/ajax/libs/gsap/3.5.1/ScrollToPlugin.min.js",
      "https://cdnjs.cloudflare.com/ajax/libs/gsap/3.5.1/ScrollTrigger.min.js",
      "https://s3-us-west-2.amazonaws.com/s.cdpn.io/16327/SplitText3.min.js",
      "https://cdnjs.cloudflare.com/ajax/libs/gsap/3.5.1/TextPlugin.min.js"
    ];

    const loadScript = (url) => {
      return new Promise((resolve, reject) => {
        const script = document.createElement("script");
        script.src = url;
        script.onload = resolve;
        script.onerror = reject;
        document.body.appendChild(script);
      });
    };

    const loadAllScripts = async () => {
      try {
        for (const url of scriptUrls) {
          await loadScript(url);
        }
        this.initializeAnimation();
      } catch (error) {
        console.error("Failed to load scripts:", error);
      }
    };

    const cssLink = document.createElement("link");
    cssLink.rel = "stylesheet";
    cssLink.href =
      "https://cdnjs.cloudflare.com/ajax/libs/animate.css/4.1.1/animate.min.css";
    document.head.appendChild(cssLink);

    loadAllScripts();
  },
  methods: {
    initializeAnimation() {
      gsap.registerPlugin(ScrollTrigger);

      const videoplay = document.getElementById("videoplay");

      let tl = gsap.timeline({
        scrollTrigger: {
          trigger: "video",
          start: "top-=300% top",
          end: "bottom+=200% bottom",
          scrub: true,
          markers: true
        }
      });

      videoplay.onloadedmetadata = function () {
        tl.to(videoplay, { currentTime: videoplay.duration });
      };

      function isTouchDevice() {
        return (
          "ontouchstart" in window ||
          navigator.maxTouchPoints > 0 ||
          navigator.msMaxTouchPoints > 0
        );
      }

      if (isTouchDevice()) {
        videoplay.play();
        videoplay.pause();
      }
    }
  }
};
</script>

<style scoped>
.notification-section {
  background-color: var(--color-primary);
  width: 100%;
  margin: 0px;
  border-radius: 100px 100px 0px 0px;
}



h2 {
  font-size: 48px;
  font-family: mondwest;
}

p {
  font-size: 18px;
}

.textbox {
  color: white;
}
</style>
