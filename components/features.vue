<template>
  <div class="features-section pt-2 pb-5 bg-white">
    <div class="pt-md-5 pt-0 p-md-0 p-4">
      <div class="d-flex justify-content-center">
        <h2 class="pt-5">Rethinking notifications</h2>
      </div>
      <div class="d-flex justify-content-center">
        <p style="max-width: 720px">Our approach is to implement AI in the device notification process, creating a soft, permeable barrier that keeps your concentration on the line without making you lose anything important.</p>
      </div>
    </div>

    <b-row class="p-md-5 px-md-0 mt-md-5 mx-md-5 mx-3 d-md-flex" align-v="center">
      <b-col lg="7" sm="12" class="d-md-flex insertscreen" data-aos="fade-right" data-aos-duration="1000">

        <video autoplay muted loop class="videofeature">
          <source src="video/feature1.mp4" type="video/mp4">
        </video>

      </b-col>
      <b-col style="text-align: left" class="ml-md-5 mt-4 mt-md-0">
        <h3>Knowing each other</h3>
        <p style="max-width: 400px">In order to provide you with the best possible service, Bottleneck AI must understand your behavioral patterns and how you interact with notifications daily.</p>
        <div class="d-md-flex align-items-center my-4">
          <b-img src="~assets/svg/icon_1_custom.svg" style="height: 40px" class="pr-3"></b-img>
          Custom AI model
        </div>
        <div class="d-md-flex align-items-center my-4">
          <b-img src="~assets/svg/icon_1_chat.svg" style="height: 40px" class="pr-3"></b-img>
          Chat-based AI training / settings
        </div>
      </b-col>
    </b-row>

    <b-row class="p-md-5 px-md-0 mt-md-5 mx-md-5 mx-3 d-md-flex mt-4" align-v="center">
      <b-col order="2" order-md="1" style="text-align: left" class="ml-md-5 mt-4 mt-md-0">
        <h3>Analyzing</h3>
        <p style="max-width: 400px">Bottleneck AI analyzes each notification you receive, without storing any private information, to understand if it's important or not.</p>
        <div class="d-md-flex align-items-center my-4">
          <b-img src="~assets/svg/icon_2_privacy.svg" style="height: 40px" class="pr-3"></b-img>
          Complete privacy
        </div>
        <div class="d-md-flex align-items-center my-4">
          <b-img src="~assets/svg/icon_2_context.svg" style="height: 40px" class="pr-3"></b-img>
          Context analysis
        </div>
        <div class="d-md-flex align-items-center my-4">
          <b-img src="~assets/svg/icon_2_search.svg" style="height: 40px" class="pr-3"></b-img>
          AI-powered context research
        </div>
      </b-col>
      <b-col order="1" order-md="2" lg="7" sm="12" class="d-md-flex insertscreen" data-aos="fade-left" data-aos-duration="1000">
        <video autoplay muted loop class="videofeature">
          <source src="video/feature2.mp4" type="video/mp4">
        </video>
      </b-col>
    </b-row>

    <b-row class="p-md-5 px-md-0 mt-md-5 mx-md-5 mx-3 d-md-flex mt-4" align-v="center">
      <b-col lg="7" sm="12" class="d-md-flex insertscreen" data-aos="fade-right" data-aos-duration="1000">
        <video autoplay muted loop class="videofeature">
          <source src="video/feature3.mp4" type="video/mp4">
        </video>
      </b-col>
      <b-col style="text-align: left" class="ml-md-5 mt-4 mt-md-0">
        <h3>Standing by your side</h3>
        <p style="max-width: 400px">Our dream is to provide users with a precious tool that can follow them through years of changing devices, keeping them focused and improving their digital well-being, starting from notifications.</p>
        <div class="d-md-flex align-items-center my-4">
          <b-img src="~assets/svg/icon_3_adaptable.svg" style="height: 40px" class="pr-3"></b-img>
          Reliable and adaptable service
        </div>
        <div class="d-md-flex align-items-center my-4">
          <b-img src="~assets/svg/icon_3_layers.svg" style="height: 40px" class="pr-3"></b-img>
          Double-layer interaction to recap notifications
        </div>
        <div class="d-md-flex align-items-center my-4">
          <b-img src="~assets/svg/icon_3_platform.svg" style="height: 40px" class="pr-3"></b-img>
          Cross-platform system
        </div>
      </b-col>
    </b-row>
  </div>
</template>

<script>
import AOS from 'aos';
import 'aos/dist/aos.css';

export default {
  name: 'features',
  mounted() {
    AOS.init();
  }
}
</script>

