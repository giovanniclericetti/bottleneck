<template>
  <div class="global-wrapper bottleneck" :style="gradientStyle">
    <div class="nav-container d-flex justify-content-between align-items-center px-md-5 px-3 shadow-sm">
      <div class="navlogo">
        <div href="#hero" @click="scrollToNotifications" style="cursor: pointer">
          <img src="~assets/svg/bottleneck.svg" alt="logo">
        </div>
      </div>
      <div class="nav d-none d-lg-block">
        <b-nav pills card-header v-b-scrollspy:nav-scroller style="background-color: #E9EDED; padding: 4px">
          <div href="#hero" class="navitem" @click="scrollToNotifications">Notifications</div>
          <div href="#features" class="navitem" @click="scrollToFeatures">Features</div>
          <div href="#layers" class="navitem" @click="scrollToLayers">Layers</div>
          <div href="#transparency" class="navitem" @click="scrollToTransparency">Transparency</div>
          <div href="#discover" class="navitem" @click="scrollToDiscover">Discover</div>
          <span class="glider" :style="{ transform: `translateX(${(sections.indexOf(activeSection) || 0) * 100}%)` }"></span>
        </b-nav>
      </div>
      <div class="nav d-none d-lg-block ">
        <button type="button" class="btn align-middle">
          <p>Download App</p>
        </button>
      </div>
      <div class="nav d-lg-none d-flex justify-content-between align-items-center">
        <b-img v-b-toggle.sidebar-right src="~assets/svg/icon_menu.svg" style="height: 40px"></b-img>
        <b-sidebar id="sidebar-right" title="" right shadow no-header>
          <div class="px-3">
            <div type="button" class="close-btn d-flex justify-content-between align-items-center" style="height: 80px;" @click="$bvModal.hide('sidebar-right')">
              <b-img v-b-toggle.sidebar-right src="~assets/svg/icon_close.svg" style="height: 40px"></b-img>
            </div>
            <b-nav-item href="#notifications" class="sidebaritem" @click="scrollToNotifications">Notifications</b-nav-item>
            <b-nav-item href="#features" class="sidebaritem" @click="scrollToFeatures">Features</b-nav-item>
            <b-nav-item href="#layers" class="sidebaritem" @click="scrollToLayers">Layers</b-nav-item>
            <b-nav-item href="#transparency" class="sidebaritem" @click="scrollToTransparency">Transparency</b-nav-item>
            <b-nav-item href="#discover" class="sidebaritem" @click="scrollToDiscover">Discover</b-nav-item>
            <button type="button" class="btn btn-big mt-3">
              <p class="sidebaritem">Download App</p>
            </button>
          </div>
        </b-sidebar>
      </div>
    </div>
    <div style="overflow-y: scroll; overflow-x: hidden">
      <section id="notifications">
        <hero />
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
      <section>
        <download />
      </section>
    </div>
    <section>
      <footerlanding />
    </section>
  </div>
</template>

<script>
export default {
  name: 'IndexPage',
  data() {
    return {
      gradientStyle: {
        background: "",
      },
      observer: null,
      activeSection: 'notifications',
      sections: ['notifications', 'features', 'layers', 'transparency', 'discover']
    };
  },
  created() {
    this.observer = new IntersectionObserver(this.onElementObserved, {
      root: this.$el,
      threshold: 0.4,
    });
  },
  mounted() {
    window.addEventListener("mousemove", this.updateGradient);
    this.$el.querySelectorAll('section[id]').forEach((section) => {
      this.observer.observe(section);
    });
  },
  beforeDestroy() {
    this.observer.disconnect();
    window.removeEventListener("mousemove", this.updateGradient);
  },
  methods: {
    updateGradient(event) {
      const x = event.clientX / window.innerWidth;
      const y = event.clientY / window.innerHeight;
      this.gradientStyle.background = `radial-gradient(circle at ${x * 100}% ${y * 100}%, #366D70, #25454D)`;
    },
    onElementObserved(entries) {
      entries.forEach(({ target, isIntersecting }) => {
        const id = target.getAttribute('id');
        if (isIntersecting) {
          console.log(id);
          this.activeSection = id;
        }
      });
    },
    scrollToNotifications() {
      const el = document.querySelector('#notifications');
      const glider = document.querySelector('.glider');
      if (el && glider) {
        el.scrollIntoView({ behavior: 'smooth' });
      }
    },
    scrollToFeatures() {
      const el = document.querySelector('#features');
      const glider = document.querySelector('.glider');
      if (el && glider) {
        el.scrollIntoView({ behavior: 'smooth' });
      }
    },
    scrollToLayers() {
      const el = document.querySelector('#layers');
      const glider = document.querySelector('.glider');
      if (el && glider) {
        el.scrollIntoView({ behavior: 'smooth' });
      }
    },
    scrollToTransparency() {
      const el = document.querySelector('#transparency');
      const glider = document.querySelector('.glider');
      if (el && glider) {
        el.scrollIntoView({ behavior: 'smooth' });
      }
    },
    scrollToDiscover() {
      const el = document.querySelector('#discover');
      const glider = document.querySelector('.glider');
      if (el && glider) {
        el.scrollIntoView({ behavior: 'smooth' });
      }
    },
  },
};
</script>
