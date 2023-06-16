<template>
  <div>
    <div class="nav-container d-flex justify-content-between align-items-center px-md-5 px-3 shadow-sm">
      <div>Bottleneck</div>
      <div class="nav d-none d-lg-block">

        <b-nav pills card-header v-b-scrollspy:nav-scroller style="background-color: #E9EDED; padding: 4px">
          <div href="#hero" class="navitem" @click="scrollToNotifications">Notifications</div>
          <div href="#features" class="navitem" @click="scrollToFeatures">Features</div>
          <div href="#layers" class="navitem" @click="scrollToLayers">Layers</div>
          <div href="#transparency" class="navitem" @click="scrollToTransparency">Transparency</div>
          <div href="#discover" class="navitem" @click="scrollToDiscover">Discover</div>
          <span class="glider" :style="{transform: `translateX(${sections.indexOf(activeSection)*100}%)`}"></span>
        </b-nav>

      </div>
      <div class="nav d-none d-lg-block ">
        <button type="button" class="btn align-middle shadow-sm">
          <p>
            Download App
          </p>
        </button>

      </div>

      <div class="nav d-lg-none d-flex justify-content-between align-items-center">
        <b-img v-b-toggle.sidebar-right src="~assets/svg/icon1.svg" style="height: 40px"></b-img>

        <b-sidebar id="sidebar-right" title="" right shadow no-header>
          <div class="px-3">
            <div type="button" class="close-btn d-flex justify-content-between align-items-center" style="height: 80px;"
                 @click="$bvModal.hide('sidebar-right')">

              <b-img v-b-toggle.sidebar-right src="~assets/svg/icon3.svg" style="height: 40px"></b-img>

            </div>
            <b-nav-item href="#hero" class="sidebaritem" @click="scrollToNotifications">Notifications</b-nav-item>
            <b-nav-item href="#features" class="sidebaritem" @click="scrollToFeatures">Features</b-nav-item>
            <b-nav-item href="#layers" class="sidebaritem" @click="scrollToLayers">Layers</b-nav-item>
            <b-nav-item href="#transparency" class="sidebaritem" @click="scrollToTransparency">Transparency</b-nav-item>
            <b-nav-item href="#discover" class="sidebaritem" @click="scrollToDiscover">Discover</b-nav-item>
            <button type="button" class="btn mt-3">
              <p class="">
                Download App
              </p>
            </button>


          </div>
        </b-sidebar>
      </div>

    </div>
    <div id="nav-scroller" style="overflow-y: scroll; ">

      <section id="hero">
        <hero/>
      </section>

      <section id="notifications">
        <notifications/>
      </section>

      <section id="features">
        <features/>
      </section>

      <section id="layers">
        <layers/>
      </section>

      <section id="transparency">
        <transparency/>
      </section>

      <section id="discover">
        <discover/>
      </section>

      <section id="download">
        <download/>
      </section>

      <section id="footer">
        <footerlanding/>
      </section>

    </div>
  </div>
</template>

<script>
export default {
  name: 'IndexPage',
  data() {

    return {
      observer: null,
      activeSection: 'notifications',
      sections: ['notifications', 'features', 'layers', 'transparency', 'discover']
    }

  },


  created() {
    this.observer = new IntersectionObserver(this.onElementObserved,
      {
        root: this.$el,
        threshold: 0.22,
      })
  },
  mounted() {
    this.$el.querySelectorAll('section[id]').forEach((section) => {
      this.observer.observe(section)
    })
  },
  deforeDestroy() {
    this.observer.disconnect()
  },
  methods: {
    onElementObserved(entries) {

      entries.forEach(({target, isIntersecting}) => {
        const id = target.getAttribute('id')
        if (isIntersecting) {
          this.activeSection='id'
        }
      })

    },
    scrollIntoView(event) {
      event.preventDefault();
      const href = event.target.getAttribute('href');
      const el = href ? document.querySelector(href) : null;
      if (el) {
        el.scrollIntoView({behavior: 'smooth'});
      }
    },
    scrollToNotifications() {
      const el = document.querySelector('#notifications');
      const glider = document.querySelector('.glider');
      if (el && glider) {
        el.scrollIntoView({behavior: 'smooth'});
        glider.style.transform = 'translateX(0)';
      }
    },
    scrollToFeatures() {
      const el = document.querySelector('#features');
      const glider = document.querySelector('.glider');
      if (el && glider) {
        el.scrollIntoView({behavior: 'smooth'});
        glider.style.transform = 'translateX(100%)';
      }
    },
    scrollToLayers() {
      const el = document.querySelector('#layers');
      const glider = document.querySelector('.glider');
      if (el && glider) {
        el.scrollIntoView({behavior: 'smooth'});
        glider.style.transform = 'translateX(200%)';
      }
    },
    scrollToTransparency() {
      const el = document.querySelector('#transparency');
      const glider = document.querySelector('.glider');
      if (el && glider) {
        el.scrollIntoView({behavior: 'smooth'});
        glider.style.transform = 'translateX(300%)';
      }
    },
    scrollToDiscover() {
      const el = document.querySelector('#discover');
      const glider = document.querySelector('.glider');
      if (el && glider) {
        el.scrollIntoView({behavior: 'smooth'});
        glider.style.transform = 'translateX(400%)';
      }
    },
  },
};
</script>

<style>

@font-face {
  font-family: "mondwest";
  src: url('./assets/fonts/mondwest/PPMondwest-Regular.ttf') format("truetype");
}

@font-face {
  font-family: "sfpro";
  src: url('./assets/fonts/sf/SF-Pro-Display-Light.otf') format("opentype");
}

.red {
  background-color: #ff0000;
}

.bottleneck {
  --color-primary: #619698;
  --color-secondary: #25454D;
  background-color: #25454D;
  font-family: 'sfpro';
  text-align: center;
}

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

.sidebaritem {
  text-align: left;
  font-size: 24px;
  z-index: 999;
  background-color: pink;
}

.sidebaritem a {
  color: #25454D;
  padding-left: 0px;
}

.navitem a {
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

@media (max-width: 768px) {

  .btn {
    background-color: none;
    border-radius: 21px;
    color: #619698;
    border-width: 1px;
    border-color: #619698;
    font-size: 24px;
    height: 46px;
  }

}


</style>
