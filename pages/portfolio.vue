<template>
  <div>
    <div class="header">
      <div class="container">
        <h2>Portfolio</h2>
      </div>
    </div>
    <section>
      <div class="container grid">
        <LazyCard
          v-for="(p, index) in data"
          :key="index"
          :title="p.title"
          :link="p.link"
          :cover="p.cover"
          :github="p.github"
          :tecs="p.tecs"
        />
      </div>
    </section>
    
  </div>
</template>

<script>
import json from "@/assets/db.json"
export default {
  layout:'pages',
  data() {
    return {
      data: json
    }
  },
}
</script>

<style lang="scss" scoped>
.header {
  background-image: url('@/assets/backportfolio.jpg');
}
h2 {
  color: #fff;
  font-weight: 800;
  font-size: 4em;
  text-transform: capitalize;
}
.aber{
  width: 100%;
  height: 200vh;
  background-color: turquoise;
}
</style>