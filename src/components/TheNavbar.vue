<template>

  <header class="bg-light">
  <nav class="container d-flex py_m pe-5">

    <img class="nav-logo img-fluid" :src="getImgUrl()" :alt="navLogoImg.name">

    <ul class="list-group-flush flex-fill d-flex justify-content-end text-uppercase m-0">
      
      <li class="list-group-item"
      v-for="(link) in navLinks" >
        <a target="_blank" class="d-flex flex-column align-items-center h-100 px-3 pt-4 " 
        :href="link.href" >

          <div class="flex-fill">{{link.name}}</div>
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

.nav-logo {
  width: 80px;
}

a {
  font-size: .75rem;
  font-weight: 800;
  color: $secondary;

  &:hover,
  &:active {
    color: $primary
  }

  .link-underline {
    margin-bottom: -1.5rem;
    background-color: $secondary;
    height: 6px;
    width: 0px;
    transition: all .3s;
  }

  &:hover .link-underline{
    background-color: $primary;
    width: 100%;
  }
}
</style>