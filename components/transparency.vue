<template>
  <div class="transparency-section pt-2 pb-0 m-0">
    <div class="pt-md-5 pt-0 p-md-0 p-4">
      <div class="d-flex justify-content-center">
        <h2 class="pt-5 text-white">Transparency and safety is our priority</h2>
      </div>
      <div class="d-flex justify-content-center">
        <p style="max-width: 800px" class="text-white">
          Our first commitment is your privacy and the
          safety of the data you share with Bottleneck AI using the service.
          We don’t sell data, we don’t need that: Bottleneck is a subscription-driven service.
          All the data analyzed by the model have the sole aim to mold your custom AI model.
          You can turn it off or customize it anytime you need.
        </p>
      </div>
    </div>

    <div class="mt-5 pb-5">
      <div class="justify-content-center imgtransparency d-flex">
        <b-img src="~assets/img/transparency.png" data-aos="fade-up" data-aos-duration="1000" class="pr-3 align-self-center"></b-img>
      </div>
    </div>
  </div>
</template>

<script>
import AOS from 'aos';
import 'aos/dist/aos.css';

export default {
  name: 'transparency',
  mounted() {
    AOS.init();
  }
}
</script>
