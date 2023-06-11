<template >
<div style="background-color: #619698;">

  <div class="discover-section pt-2 pb-5" >
    <div class="textbox pt-5">
      <h2 class="pt-5">Discover all Bottleneck’s features</h2>
      <div class="d-flex justify-content-center">
        <p style="max-width: 780px">
          We don’t limit ourselves to better notifications, we aspire to
          provide users with a tool able to free them from the fomo we all
          suffer, due to our close relation with digital device. Want to know more? Check this video:
        </p>
      </div>
    </div>

    <div class="my-5 pb-5">
      <div>
        <video style="width: 60%; border-radius: 24px" controls>
          <source src="https://www.w3schools.com/html/mov_bbb.mp4" type="video/mp4">
        </video>
      </div>
    </div>
  </div> </div>

</template>

<script>
export default {
  name: "discover"
}
</script>

<style scoped>

.discover-section {
  background-color: white;
  width: 100%;
  margin: 0px;
  border-radius: 0px 0px 100px 100px;
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

</style>
