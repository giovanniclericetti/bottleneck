<template>
  <div class="hero-section p-5" :style="gradientStyle">

    <div style="margin-top: 15vh">
      <h1 class="mt-5 pt-5 m-0">Bottleneck</h1>
      <div class="justify-content-center d-flex">
        <div class="subtitle justify-content-center d-flex">
          <h3>AI-powered dashboard to finally receive notifications in a healthy and right way</h3>
        </div>
      </div>

      <div class="herodash d-flex justify-content-center mt-5  mb-5">
        <img src="~assets/img/dashboard.png">
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "hero",
  data() {
    return {
      gradientStyle: {
        background: "",
      },
    };
  },
  mounted() {
    window.addEventListener("mousemove", this.updateGradient);
  },
  beforeDestroy() {
    window.removeEventListener("mousemove", this.updateGradient);
  },
  methods: {
    updateGradient(event) {
      const x = event.clientX / window.innerWidth;
      const y = event.clientY / window.innerHeight;
      const gradientColor = `radial-gradient(circle at ${x * 100}% ${y * 100}%, #366D70, #25454D)`;
      this.gradientStyle.background = gradientColor;
    },
  },
};
</script>

<style scoped>
.hero-section {
  min-height: 100vh;
}

h1 {
  font-family: "mondwest";
  font-size: 10vw;
  text-align: center;
  color: white;
}

h3 {
  color: white;
  font-size: 32px;
}

.subtitle {
  max-width: 600px;
}

.herodash img {
  height: 80vh;
}

@media (max-width: 768px) {
  h1 {
    font-size: 15vw;
  }

  h3 {
    color: white;
    font-size: 20px;
  }

  .herodash img {
    width: 80vw;
    height: auto;
  }

  .hero-section {
    min-height: auto;
  }
}
</style>
