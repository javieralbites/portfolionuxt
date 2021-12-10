<template>
  <div class="card">
    <img loading="lazy" :src="cover" alt="cover" />
    <div class="content">
      <h2>{{ title }}</h2>
      <span v-for="(tec, index) in tecs" :key="index">{{ tec }}</span>
      <div class="links">
        <a :href="link" target="_blank">View Web</a>
        <a :href="github" target="_blank">Github</a>
      </div>
      <div class="index">
        {{ index + 1 }}
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    title: String,
    cover: String,
    link: String,
    github: String,
    tecs: Array,
    index: Number,
  },
}
</script>

<style lang="scss" scoped>
.card {
  width: 100%;
  height: 350px;
  // border: 1px #fff solid;
  color: #fff;
  margin: 2em 0;
  display: flex;
  overflow: hidden;
  // background: #000;
  background-color: #18191A;
  // box-shadow: 
  //      inset 0 -3em 3em rgba(0,0,0,0.1), 
  //            0 0  0 2px rgb(255,255,255),
  //            0.3em 0.3em 1em rgba(0,0,0,0.3);
  border-radius: 10px;
  box-shadow: 0 1px 2px rgba(0,0,0,0.07), 
                0 2px 4px rgba(0,0,0,0.07), 
                0 4px 8px rgba(0,0,0,0.07), 
                0 8px 16px rgba(0,0,0,0.07),
                0 16px 32px rgba(0,0,0,0.07), 
                0 32px 64px rgba(0,0,0,0.07);
  @media (max-width: 992px) {
    height: auto;
    flex-direction: column;
  }
}
img {
  width: 60%;
  height: 100%;
  object-fit: cover;
  transition: cubic-bezier(0.075, 0.82, 0.165, 1) 2s;
  // clip-path: polygon(0 0, 90% 0, 76% 100%, 0% 100%);
  &:hover {
    // clip-path: polygon(0 0, 100% 0, 100% 100%, 0% 100%);
    // transform: scale(1.1);
  }
  @media (max-width: 992px) {
    width: 100%;
    height: 180px;
  }
}
.content {
  width: 40%;
  padding: 2em;
  position: relative;
  h2 {
    font-size: 2em;
    line-height: 32px;
    margin-bottom: 0.7em;
    @media (max-width: 992px) {
      margin-bottom: 0.5em;
      font-size: 1.75em;
    }
  }
  span {
    color: #fff;
    border: #fff 1px solid;
    border-radius: 15px;
    margin-right: 1em;
    margin-bottom: .9em;
    padding: 0.3em 0.8em;
    font-size: 0.8em;
    font-weight: 300;
    display: inline-block;
    @media (max-width:992px) {
      margin-bottom: .7em;
    }
  }
  .links {
    z-index: 10;
    position: absolute;
    bottom: 0;
    left: 0;
    width: 100%;
    padding: 2em;
    display: flex;
    justify-content: space-between;
    @media (max-width: 992px) {
      margin-top: 1em;
      position: relative;
      padding: 0;
    }
    a {
      background: #242526;
      text-decoration: none;
      color: #fff;
      // border: 1px solid #fff;
      cursor: pointer;
      padding: 1em 2em;
      transition: 0.2s all ease;
      border-radius: 5px;
      &:hover {
        // opacity: 0.9;
        background: #fff;
        color:#000
      }
    }
  }
  .index {
    font-weight: 700;
    user-select: none;
    font-size: 330px;
    line-height: 100%;
    opacity: 0.2;
    position: absolute;
    top: 0;
    right: -50px;
    height: 100%;
    color: white;
    @media (max-width: 992px) {
    //   font-size: 7em;
    //   right: -20px;
    //   font-weight: 800;
     display: none;
    }
  }
  @media (max-width: 992px) {
    width: 100%;
    padding: 1em;

  }
}
</style>