<template>
  <div class="header" >
    <!-- <img :src="img" :alt="title" /> -->
    <!-- <img src="@/assets/backportfolio.jpg" alt="a"> -->
    <div class="container">
      <h2>{{ title }}</h2>
      <h3>{{ img }}</h3>
      
    </div>
    <!-- <img :src="img" alt="a" /> -->
  </div>
</template>

<script>
export default {
  props: {
    title: {type: String, default:'javier'},
    img: String,
  }
}
</script>

<style lang="scss" scoped>
.header {
  position: relative;
  height: 360px;
  width: 100%;
  // background-image: url('@/assets/backportfolio.jpg');
    background-position: center;
    background-repeat: no-repeat;
    background-size: cover;
  // background: chartreuse;
  .container {
    z-index: 10;
    h2 {
      color: #fff;
      font-weight: 800;
      font-size: 4em;
      text-transform: capitalize;
    }
    
  }
  
}
</style>