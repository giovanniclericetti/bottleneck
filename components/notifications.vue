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

          src="~assets/video/notifications.mp4"

        />


      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "notifications",
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
