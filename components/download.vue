<template>
<div class="download-section py-5">

  <b-row class="p-md-5 px-md-0 mt-md-5 mx-md-5 mx-3 d-md-flex" align-v="center">

    <b-col lg="8" sm="12" class="d-md-flex" data-aos="fade-right" data-aos-duration="1000">
     <b-img style="width: 100%" src="~assets/img/feature_3.png" ></b-img>
    </b-col>

    <b-col style="text-align: left" class="ml-md-5 mt-4 mt-md-0">

      <h3>Put a cork in your <br>
        notifications! </h3>
      <p style="max-width: 400px">Bottleneck is available for every platform, <br> the system doesn’t change..</p>

      <button type="button" class="btn align-middle">
        <p>
          Download App
        </p>
      </button>

    </b-col>
  </b-row>

</div>

</template>

<script>
export default {
  name: "download"
}
</script>

<style scoped>

.btn{
  height: 38px;
  background-color: none;
  border-radius: 21px;
  color: white;
  border-width: 1px;
  border-color: white;
  font-family: 'mondwest';
  font-size: 20px;
}

.btn:hover{
  background-color: white;
  color: #25454D;
}

.download-section{

  background-color: #619698;
  color: white;

}

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

</style>
