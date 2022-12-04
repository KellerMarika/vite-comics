<template lang="">

  <header class="bg-light">
  <nav class="container d-flex py-3">

    <img class="nav-logo img-fluid" src="../assets/dc-logo.png" :alt="navLogoImg.name">

    <ul class="list-group-flush flex-fill d-flex justify-content-end text-uppercase p-0 m-0">
      <li class="list-group-item d-flex flex-column"
      v-for="(link) in navLinks" >
        <a class="d-inline-block px-3 py-4" 
        :href="link.href">{{link.name}}
        <div class="link-underline"></div>
      </a>       
      </li>
    </ul>
   
  </nav>
</header>
</template>

<script>
export default {
  data() {
    return {
      navLogoImg: {
        name: "dc-logo"
      },

      navLinks: [
        {
          name: "characters",
          href: "https://www.dc.com/characters",
        },
        {
          name: "comics",
          href: "https://www.dc.com/comics",
        },
        {
          name: "movies",
          href: "https://www.dc.com/movies",
        },
        {
          name: "tv",
          href: "https://www.dc.com/tv",

        },
        {
          name: "games",
          href: "https://www.dc.com/games",

        },
        {
          name: "collectibles",
          href: "https://shop.dc.com/coming-soon/",
        },
        {
          name: "videos",
          href: "https://www.dc.com/videos",
        },
        {
          name: "fans",
          href: "https://community.dcuniverseinfinite.com/",
        },
        {
          name: "news",
          href: "https://www.dc.com/news",
        },
        {
          name: "shop",
          href: "https://www.dc.com/#",
        }
      ],
    }
  },
  methods: {

     getImgUrl() {
      return new URL(`../assets/${this.navLogoImg.name}.png`, import.meta.url)
    } 
  }

}
</script>

<style scoped lang="scss">
@use "../styles/partials/variables" as *;

* {
  border: 1px solid greenyellow
}

.nav-logo {
  width: 80px;
}

a {
  font-size: .75rem;
  font-weight: 800;
  color: $secondary;

  .link-underline {
    background-color: red;
    height: 8px;
    width: 100%;
  }

  &:hover,
  &:active {
    color: $primary
  }

}
</style>