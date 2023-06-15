<template>
  <div>
    <div class="nav-container d-flex justify-content-between align-items-center px-5 shadow-sm" >
      <div>Bottleneck</div>
      <div class="nav d-none d-md-block">

        <b-nav pills card-header v-b-scrollspy:nav-scroller style="background-color: #E9EDED; padding: 4px">
          <b-nav-item href="#hero" class="navitem" @click="scrollToNotifications">notifications</b-nav-item>
          <b-nav-item href="#features" class="navitem" @click="scrollToFeatures">features</b-nav-item>
          <b-nav-item href="#layers" class="navitem" @click="scrollToLayers">layers</b-nav-item>
          <b-nav-item href="#transparency" class="navitem" @click="scrollToTransparency">transparency</b-nav-item>
          <b-nav-item href="#discover" class="navitem" @click="scrollToDiscover">discover</b-nav-item>
          <span class="glider"></span>
        </b-nav>

      </div>
      <div class="nav d-none d-md-block" >
        <button type="button" class="btn align-middle shadow-sm">
          <p>
            Download App
          </p>
        </button>

      </div>

      <div class="nav d-md-none d-block">
        <b-button v-b-toggle.sidebar-right>Toggle Sidebar</b-button>
        <b-sidebar id="sidebar-right" title="Sidebar" right shadow>
          <div class="px-3 py-2">
              <b-nav-item href="#hero" class="sidebaritem" @click="scrollToNotifications">notifications</b-nav-item>
              <b-nav-item href="#features" class="sidebaritem" @click="scrollToFeatures">features</b-nav-item>
              <b-nav-item href="#layers" class="sidebaritem" @click="scrollToLayers">layers</b-nav-item>
              <b-nav-item href="#transparency" class="sidebaritem" @click="scrollToTransparency">transparency</b-nav-item>
              <b-nav-item href="#discover" class="sidebaritem" @click="scrollToDiscover">discover</b-nav-item>
          </div>
        </b-sidebar>
      </div>

    </div>
    <div id="nav-scroller" style="overflow-y: scroll; ">
      <section id="hero">
        <hero />
      </section>
      <section id="notifications">
        <notifications />
      </section>
      <section id="features">
        <features />
      </section>
      <section id="layers">
        <layers />
      </section>
      <section id="transparency">
        <transparency />
      </section>
      <section id="discover">
        <discover />
      </section>
      <section id="download">
        <download />
      </section>
      <section id="footer">
        <footerlanding />
      </section>
    </div>
  </div>
</template>

<script>
export default {
  name: 'IndexPage',
  methods: {
    scrollIntoView(event) {
      event.preventDefault();
      const href = event.target.getAttribute('href');
      const el = href ? document.querySelector(href) : null;
      if (el) {
        el.scrollIntoView({ behavior: 'smooth' });
      }
    },
    scrollToNotifications() {
      const el = document.querySelector('#notifications');
      const glider = document.querySelector('.glider');
      if (el && glider) {
        el.scrollIntoView({ behavior: 'smooth' });
        glider.style.transform = 'translateX(0)';
      }
    },
    scrollToFeatures() {
      const el = document.querySelector('#features');
      const glider = document.querySelector('.glider');
      if (el && glider) {
        el.scrollIntoView({ behavior: 'smooth' });
        glider.style.transform = 'translateX(100%)';
      }
    },
    scrollToLayers() {
      const el = document.querySelector('#layers');
      const glider = document.querySelector('.glider');
      if (el && glider) {
        el.scrollIntoView({ behavior: 'smooth' });
        glider.style.transform = 'translateX(200%)';
      }
    },
    scrollToTransparency() {
      const el = document.querySelector('#transparency');
      const glider = document.querySelector('.glider');
      if (el && glider) {
        el.scrollIntoView({ behavior: 'smooth' });
        glider.style.transform = 'translateX(300%)';
      }
    },
    scrollToDiscover() {
      const el = document.querySelector('#discover');
      const glider = document.querySelector('.glider');
      if (el && glider) {
        el.scrollIntoView({ behavior: 'smooth' });
        glider.style.transform = 'translateX(400%)';
      }
    },
  },
};
</script>

<style scoped>
.nav-container {
  color: #25454D;
  font-family: 'mondwest';
  font-size: 20px;
  height: 80px;
  position: fixed;
  z-index: 999;
  width: 100%;
  background-color: white;
}

.nav {
  align-items: center;
  font-size: 20px;
  border-radius: 99px;
  cursor: pointer;
  margin: 0px;
  transition: color 0.15s ease-in;
}

.navitem {
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
  z-index: 999;
}

.navitem a{
  color: #25454D;
}

.glider {
  position: absolute;
  display: flex;
  height: 54px;
  width: 150px;
  background-color: #8FBCBE;
  z-index: 1;
  border-radius: 99px;
  transition: 0.25s ease-out;
}

#nav-scroller {
  margin-top: 0px;
}

.btn {
  height: 38px;
  background-color: none;
  border-radius: 21px;
  color: #619698;
  border-width: 1px;
  border-color: #619698;
}

.btn:hover {
  background-color: #619698;
  color: white;
}
</style>
