<template>
  <div>
    <div class="header">
      <div class="container">
        <h2>About Me</h2>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  layout:'pages',
}
</script>

<style lang="scss" scoped>
.header {
  background-image: url('@/assets/backabout.jpg');
}
h2 {
  color: #fff;
  font-weight: 800;
  font-size: 4em;
  text-transform: capitalize;
}
</style>