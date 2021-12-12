<template>
  <div>
    <div class="header">
      <div class="container">
        <h2>About Me</h2>
      </div>
    </div>
    <div class="container about">
      <!-- <p>Hi, my name is Javier, soy graduado i am frontend developer since a couple years, i make websites with </p> -->
      <img
        src="https://lh3.googleusercontent.com/ogw/ADea4I44Z9TRmLjahDBWs-MrAUPghdb2PKVRBD9oS1dc5A=s200-c-mo"
        alt="foto"
      />
      <p>
        Hola, mi nombre es Javier, soy graduado de la carrera profesional de
        Ingeniería de Sistemas, trabajo como Frontend Developer Freelancer desde
        hace unos meses. Realizo Páginas Web, SPAs(Single Page Aplication)
        Aplicaciones Web con tecnologías modernas como Vue y todo su ecosistema:
        Vue Router, Vuex, Vuetify, Nuxt, etc.
      </p>
    </div>
    <Footer />
  </div>
</template>

<script>
export default {
  layout: 'pages',
}
</script>

<style lang="scss" scoped>
.header {
  background-image: url('@/assets/backabout.jpg');
  h2 {
    color: #fff;
    font-weight: 800;
    font-size: 4em;
    text-transform: capitalize;
  }
}
.about {
  display: flex;
  justify-content: space-between;
  gap: 3em;
  margin-top: 2em;
  margin-bottom: 2em;
  @media (max-width:620px) {
    flex-direction: column;
    gap: 1em;
  }
  img {
    transition: cubic-bezier(0.075, 0.82, 0.165, 1) filter 5s ;
    filter: grayscale(0.8);
    width: 100%;
    &:hover {
      filter: grayscale(0);
    }
  }
  p {
    margin-top: auto;
    margin-bottom: auto;
    color: #fff;
    line-height: 25px;
  }
}
</style>