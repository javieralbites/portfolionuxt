<template>
  <div class="hero">
    <div class="link">
      <nuxt-link
        to="/about"
        @mouseenter.native="activeBackPortfolio()"
        @mouseleave.native="activeBackPortfolio()"
        >Javier albites</nuxt-link
      >
      <span>About ME &nbsp; &#8212; &nbsp; </span>
    </div>
    <div class="link">
      <nuxt-link
        to="/portfolio"
        @mouseenter.native="activeBackAbout()"
        @mouseleave.native="activeBackAbout()"
        >Frontend developer</nuxt-link
      >
      <span>portfolio &nbsp; &#8212; &nbsp; </span>
    </div>
    <div class="links">
      <!-- <NuxtLink class="link" to="/portfolio"     >PORTFOLIO</NuxtLink>
      <NuxtLink class="link" to="/about"  >ABOUT ME</NuxtLink> -->
    </div>
    <img
      class="backportfolio"
      :class="{ backportfolioapear: backportfolioActive }"
      src="@/assets/backabout.jpg"
      alt="about"
    />
    <img
      class="backabout"
      :class="{ backaboutapear: backaboutActive }"
      src="@/assets/backportfolio.jpg"
      alt="about"
    />
    <div class="hero-contact">
      <h4>Contact Me</h4>
      <p>javieralbite@gmail.com</p>
      <ul>
        <!-- <li>Facebook</li> -->
        <li>LinkedIn</li>
        <li>Telegram</li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  layout: 'pages',
  data() {
    return {
      backportfolioActive: false,
      backaboutActive: false,
    }
  },
  methods: {
    activeBackAbout() {
      this.backaboutActive = !this.backaboutActive
    },
    activeBackPortfolio() {
      this.backportfolioActive = !this.backportfolioActive
    },
  },
}
</script>

<style lang="scss" scoped >
.hero {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: flex-end;
  height: 100vh;
  padding: 6em;
  @media (max-width: 992px) {
    padding: 2em;
  }
  .link {
    z-index: 100;
    display: flex;
    align-items: center;
    @media (max-width: 992px) {
      margin: 0 auto;
    }
    span {
      text-transform: uppercase;
      font-size: 2em;
      font-weight: 700;
      // -webkit-text-stroke: 1px #fff;
      opacity: 0;
      transform: translateX(20px);
      transition: ease-in 0.5s;
      background: transparent;
      text-shadow: 2px 2px 0 #fff, 2px -2px 0 #fff, -2px 2px 0 #fff,
        -2px -2px 0 #fff, 2px 0px 0 #fff, 0px 2px 0 #fff,
        -2px 0px 0 #fff, 0px -2px 0 #fff;
      @media (max-width: 1024px) {
        display: none;
      }
    }
    a {
      color: #fff;
      text-decoration: none;
      text-transform: uppercase;
      font-size: 5em;
      font-weight: 900;
      opacity: 0.85;
      order: 1;
      &:hover {
        opacity: 1;
        ~ span {
          opacity: 1;
          transform: translateX(0px);
        }
      }
      @media (max-width: 1400px) {
        font-size: 4em;
      }
      @media (max-width: 1200px) {
        font-size: 3.5em;
      }
      @media (max-width: 1024px) {
        font-size: 4em;
      }
      @media (max-width: 992px) {
        font-size: 2em;
        text-align: center;
        margin-bottom: 1em;
      }
    }
  }
}
img {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  width: 100%;
  height: 100%;
  object-fit: cover;
  opacity: 0;
  transition: opacity 0.3s ease-in;
  &.backabout {
    &.backaboutapear {
      opacity: 1;
    }
  }
  &.backportfolio {
    &.backportfolioapear {
      opacity: 1;
    }
  }
}
.hero-contact {
  position: absolute;
  bottom: 0;
  left: 0;
  padding: 3em;
  color: #fff;
  @media (max-width: 992px) {
    padding: 2em;
  }
  p {
    margin: 0.5em 0;
  }
  ul {
    list-style: none;
    display: flex;
    li {
      margin-right: 1em;
      cursor: pointer;
    }
  }
}
</style>
