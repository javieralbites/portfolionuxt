<template>
  <footer>
    <div class="container grid">
      <h2>Contact me</h2>
      <h3>javieralbite@gmail.com</h3>
      <div class="links">
        <a href="https://www.facebook.com/javier.albites.90/">Facebook</a>
        <a href="https://www.linkedin.com/in/javieralbites/">LinkedIn</a>
        <a href="https://t.me/javierdevfront">Telegram</a>
      </div>
    </div>
  </footer>
</template>

<script>
export default {}
</script>

<style lang="scss" scoped>
footer {
  background-color: #18191a;
  padding-top: 4em;
  padding-bottom: 5em;
  h2 {
    color: azure;
    text-align: center;
    font-size: 2em;
    margin-bottom: 0.5em;
  }
  h3{
      text-align: center;
      color: #fff;
      font-size: smaller;
  }
  .links {
    display: flex;
    justify-content: space-around;
    align-items: center;
    margin-top: 3em;
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
        color: #000;
      }
      @media (max-width:620px) {
        padding: .8em 1.5em;
        font-size: smaller;
      }
    }
  }
}
</style>