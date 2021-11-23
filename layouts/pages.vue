<template>
  <div class="app">
    <!-- <h1>calla</h1> -->
    <nav>
      <NuxtLink to="/">
        <img src="@/assets/logo.png" alt="logo" />
      </NuxtLink>
      <ul>
        <NuxtLink tag="li" to="/"> Home </NuxtLink>
        <NuxtLink tag="li" to="/portfolio"> Portfolio </NuxtLink>
        <NuxtLink tag="li" to="/about"> About Me </NuxtLink>
      </ul>
    </nav>
    <Nuxt />
    <transition name="home">
      <div class="loading" v-if="!load">
        <img src="@/assets/logo.png" alt="logo" />
      </div>
    </transition>
    <!-- <div class="loading"  :class="{loadingActive : load}">
      <img src="@/assets/logo.png" alt="logo" />
      
    </div> -->
  </div>
</template>

<script>
export default {
  data() {
    return {
      load: false,
    }
  },
  transition: 'home',
  methods: {
    updateScroll(){
      const header = document.querySelector("nav");
      header.classList.toggle("sticky", window.scrollY > 0);
    }
  },
  mounted() {
    window.addEventListener("scroll", this.updateScroll);
    document.onreadystatechange = () => {
      if (document.readyState === 'complete') {
        setTimeout(() => {
          this.load = true
        }, 2000)
      }
    }
  },
}
</script>

<style lang="scss" scoped>
nav {
  width: 100%;
  position: fixed;
  background: rgba(0, 0, 0, 0.85);
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 1.5em 4em;
  z-index: 1000;
  transition: .2s ease-in;
  &.sticky{
    padding: .8em 4em;
  }
  @media (max-width: 992px) {
    padding: 0.8em 1.8em;
  }
  img {
    height: 2em;
    @media (max-width: 992px) {
      height: 1.5em;
    }
  }
  ul {
    list-style: none;
    display: flex;
    align-items: center;
    li {
      padding: 0.5em 1em;
      cursor: pointer;
      color: #fff;
      opacity: 0.8;
      &.nuxt-link-exact-active {
        opacity: 1;
        font-weight: bold;
      }
      &:hover {
        opacity: 1;
      }
      @media (max-width: 992px) {
        padding: 0.5em 0.7em;
      }
    }
    li:first-child {
      @media (max-width: 992px) {
        display: none;
      }
    }
  }
}
.loading {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  width: 100%;
  height: 100vh;
  background: rgba(0, 0, 0, 0.98);
  z-index: 1000000;
  position: fixed;
  top: 0;
  left: 0;
  transition: 0.8s all ease-in-out;
  color: #fff;
  // &.loadingActive{
  //   opacity: 0;
  // }
}
.home-enter-active,
.home-leave-active {
  transition: opacity 0.5s ease-in-out;
}
.home-enter,
.home-leave-active {
  opacity: 0;
}
</style>