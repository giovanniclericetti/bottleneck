<template>
  <div style="background-color: white" class="pb-5">

    <div class="textbox pt-md-5 pt-5 p-md-0 p-4">
      <h2 class="pt-5">
        Rethinking notifications
      </h2>

      <div class="d-flex justify-content-center">

        <p style="max-width: 720px"> Our approach is to implement AI in the device notification
          process, creating a soft, permeable, barrier, that keep your concentration on the line,
          without making you lose anything important.</p></div>
    </div>


    <b-row class="p-md-5 px-md-0 mt-md-5 mx-md-5 mx-3 d-md-flex" align-v="center">

      <b-col lg="7" sm="12" class="d-md-flex insertscreen" data-aos="fade-right" data-aos-duration="1000">
        <b-img src="~assets/img/feature_1.png" fluid></b-img>
      </b-col>

      <b-col style="text-align: left" class="ml-md-5 mt-4 mt-md-0">

        <h3>Knowing each other</h3>
        <p style="max-width: 400px">In order to provide you the best service possible, Bottleneck AI must get into your
          behavioural patterns and how you behave with notification, daily.</p>

        <div class="d-md-flex align-items-center my-4">
          <b-img src="~assets/svg/icon1.svg" style="height: 40px" class="pr-3"></b-img>
          Custom AI model
        </div>

        <div class="d-md-flex align-items-center my-4">
          <b-img src="~assets/svg/icon2.svg" style="height: 40px" class="pr-3"></b-img>
          Chat-based AI training / settings
        </div>

        <div class="d-md-flex align-items-center my-4">
          <b-img src="~assets/svg/icon3.svg" style="height: 40px" class="pr-3"></b-img>
          Reliable and adaptable service
        </div>

      </b-col>

    </b-row>

    <b-row class="p-md-5 px-md-0 mt-md-5 mx-md-5 mx-3 d-md-flex mt-4" align-v="center">

      <b-col order="2" order-md="1" style="text-align: left" class="ml-md-5 mt-4 mt-md-0">

        <h3>Analyzing</h3>
        <p style="max-width: 400px">Bottleneck AI analyses each notification you receive, without storing any private information, to understand if that’s important, or not.</p>

        <div class="d-md-flex align-items-center my-4">
          <b-img src="~assets/svg/icon1.svg" style="height: 40px" class="pr-3"></b-img>
          Complete privacy        </div>

        <div class="d-md-flex align-items-center my-4">
          <b-img src="~assets/svg/icon2.svg" style="height: 40px" class="pr-3"></b-img>
          Context analysis
        </div>

        <div class="d-md-flex align-items-center my-4">
          <b-img src="~assets/svg/icon3.svg" style="height: 40px" class="pr-3"></b-img>
          AI powered context research
        </div>
      </b-col>

      <b-col order="1" order-md="2" lg="7" sm="12" class="d-md-flex insertscreen" data-aos="fade-left" data-aos-duration="1000">
        <b-img src="~assets/img/feature_2.png" fluid></b-img>
      </b-col>

    </b-row>

    <b-row class="p-md-5 px-md-0 mt-md-5 mx-md-5 mx-3 d-md-flex mt-4" align-v="center">

      <b-col lg="7" sm="12" class="d-md-flex insertscreen" data-aos="fade-right" data-aos-duration="1000">
        <b-img src="~assets/img/feature_3.png" fluid></b-img>
      </b-col>

      <b-col style="text-align: left" class="ml-md-5 mt-4 mt-md-0">

        <h3>Standing by your side</h3>
        <p style="max-width: 400px">Our dream is to provide user a precious tool able to follow them through years of changing devices, keeping them focussed and improving their digital wellbeing: starting from notifications.</p>

        <div class="d-md-flex align-items-center my-4">
          <b-img src="~assets/svg/icon1.svg" style="height: 40px" class="pr-3"></b-img>
          Reliable and adaptable service
        </div>

        <div class="d-md-flex align-items-center my-4">
          <b-img src="~assets/svg/icon2.svg" style="height: 40px" class="pr-3"></b-img>
          Double layer interaction to recap notifications
        </div>

        <div class="d-md-flex align-items-center my-4">
          <b-img src="~assets/svg/icon3.svg" style="height: 40px" class="pr-3"></b-img>
          Cross platform system
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

<style scoped>

h2 {
  font-size: 48px;
  font-family: mondwest;
}

h3 {
  font-size: 36px;
  font-family: mondwest;
}


p {
  font-size: 18px;
}

@media (max-width: 768px) {

  h2 {
    font-size: 32px;
    font-family: mondwest;
  }

  h3{
    font-size: 28px;
  }



}

</style>
