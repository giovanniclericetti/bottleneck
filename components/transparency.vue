<template>

  <div class="transparency-section pt-2 pb-0">
    <div class="textbox pt-md-5 pt-5 p-md-0 p-4">
      <h2 class="pt-5">Transparency and safety is our priority</h2>
      <div class="d-flex justify-content-center">
        <p style="max-width: 800px">
          Our first commitment is your privacy and the
          safety of the data you share with Bottleneck AI using the service.
          We don’t sell data, we don’t need that: Bottleneck is a subscription-driven service.
          All the data analysed by the model have the only aim to mould your custom AI model.
          You can turn it off or customise it, anytime you need.
        </p>
      </div>
    </div>

    <div class="my-5 pb-5">
      <div>
        <img class="giftransparency" style="max-height: 40vh" data-aos="fade-up" data-aos-duration="1000"
             src="https://cdn.vox-cdn.com/thumbor/iaVMlcV5rj0OuPejZ7HyqYslLZk=/0x0:800x333/1400x788/filters:focal(334x72:462x200):format(gif)/cdn.vox-cdn.com/uploads/chorus_image/image/55278741/gatsby.0.gif"">
        </img>
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

<style scoped>

.giftransparency{
  max-height: 40vh
}

.transparency-section {
  background-color: #25454D;
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
  color: white;
}

@media (max-width: 768px) {

  h2 {
    font-size: 32px;
    font-family: mondwest;
  }

  .giftransparency{
    width: 90%
  }}

</style>
