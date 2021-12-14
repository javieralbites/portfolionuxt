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
          :index="index"
        />
      </div>
    </section>
    <Footer/>
  </div>
</template>

<script>
import json from "@/assets/db.json"
export default {
  layout:'pages',
  head: {
    title: 'Javier Albites | Porfolio',
    meta: [
      {
        hid: 'description',
        name: 'description',
        content: 'Portfolio'
      },
      {
          hid: 'twitter:title',
          name: 'twitter:title',
          content: 'Javier Albites | Porfolio'
        },
        {
          hid: 'twitter:description',
          name: 'twitter:description',
          content: 'Portfolio'
        },
        {
          hid: 'twitter:image',
          name: 'twitter:image',
          content: 'https://res.cloudinary.com/ddzblkqfa/image/upload/v1639485524/portfolio/omgportfolio_kjqgvt.png'
        },
        {
          hid: 'twitter:image:alt',
          name: 'twitter:image:alt',
          content: 'Javier Albites | Porfolio'
        },
        {
          hid: 'og:title',
          property: 'og:title',
          content: 'Javier Albites | Porfolio'
        },
        {
          hid: 'og:description',
          property: 'og:description',
          content: 'Portfolio'
        },
        {
          hid: 'og:image',
          property: 'og:image',
          content: 'https://res.cloudinary.com/ddzblkqfa/image/upload/v1639485524/portfolio/omgportfolio_kjqgvt.png'
        },
        {
          hid: 'og:image:secure_url',
          property: 'og:image:secure_url',
          content: 'https://res.cloudinary.com/ddzblkqfa/image/upload/v1639485524/portfolio/omgportfolio_kjqgvt.png'
        },
        {
          hid: 'og:image:alt',
          property: 'og:image:alt',
          content: 'Javier Albites | Porfolio'
        }
    ],
  },
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
  // background-attachment: fixed;
}
h2 {
  color: #fff;
  font-weight: 800;
  font-size: 4em;
  text-transform: capitalize;
  @media (max-width:920px) {
    font-size: 3.5em;
    // font-weight: 600;
  }
}
</style>