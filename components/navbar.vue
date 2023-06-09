<template>

<div class="nav d-flex px-5 justify-content-between align-items-center">

<div>
    Bottleneck
</div>

      <div class="tabs d-none d-lg-flex" style="color: var(--color-secondary)">

        <input type="radio" id="radio-1" name="tabs" checked />

        <label class="tab" for="radio-1" >Notification</label>

        <input type="radio" id="radio-2" name="tabs" />

        <label for="radio-2" class="tab" >  <a href="#features"> Features </a>  </label>

        <input type="radio" id="radio-3" name="tabs" />

        <label class="tab" for="radio-3">Layers</label>

        <input type="radio" id="radio-4" name="tabs" />

        <label class="tab" for="radio-4">Trasparance</label>

        <input type="radio" id="radio-5" name="tabs" />

        <label class="tab" for="radio-5">Discover</label>

        <span class="glider"></span>

      </div>



  <div>
    <button type="button" class="btn align-middle">
      <p>
        Download App
      </p>
    </button>



  </div>
</div>


</template>

<script>
export default {
  name: "navbar"
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
}

.btn:hover{
  background-color: white;
  color: #25454D;
}

.nav{
  color: white;
  font-family: 'mondwest';
  font-size: 20px;
  height: 100px;
  position: fixed;
  z-index: 999;
  width: 100%;
}


.tabs {
  display: flex;
  background-color: #fff;
  border-radius: 99px;
  padding: 4px;
}

.tabs * {
  z-index: 2;
}

input[type=radio] {
  display: none;
}

.tab {
  display: flex;
  align-items: center;
  justify-content: center;
  height: 54px;
  width: 150px;
  font-size: 20px;
  border-radius: 99px;
  cursor: pointer;
  margin: 0px;
  transition: color 0.15s ease-in;
}

a{
  color: var(--color-secondary);
  text-decoration: none;
}

a:hover {
  text-decoration: none;
}

input[type=radio]:checked + label {
  color: white;
}

input[id=radio-1]:checked ~ .glider {
  transform: translateX(0);
}

input[id=radio-2]:checked ~ .glider {
  transform: translateX(100%);
}

input[id=radio-3]:checked ~ .glider {
  transform: translateX(200%);
}

input[id=radio-4]:checked ~ .glider {
  transform: translateX(300%);
}

input[id=radio-5]:checked ~ .glider {
  transform: translateX(400%);
}

.glider {
  position: absolute;
  display: flex;
  height: 54px;
  width: 150px;
  background-color: var(--color-primary);
  z-index: 1;
  border-radius: 99px;
  transition: 0.25s ease-out;

}

@media (max-width: 700px) {
  .tabs {
    transform: scale(0.6);
  }
}





</style>
