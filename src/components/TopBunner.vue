<template>
  <article class="top-bunner py_l">
    <div class="container">
      <!--   <img src="../assets/buy-comics-digital-comics.png" alt=""> -->
      <ul class="list-group-flush d-flex justify-content-around  align-items-center m-0 p-0">
        <li class="list-group-item"
            v-for="(link, i) in bunnerLinks">
          <a class="d-flex align-items-center"  target="_blank" 
          :href="link.href">
            <img class="link-img img-fluid"
            :src="getImgUrl(link.img.name, link.img.format)" 
            :alt="link.imgName">

            <h6 class="text-uppercase small">{{ link.name }}</h6>
          </a>
        </li>
      </ul>
    </div>
  </article>
</template>

<script>
export default {
  data() {
    return {
      bunnerLinks: [
        {
          name: "digital comics",
          href: "https://www.dcuniverseinfinite.com/",
          img: {
            name: "buy-comics-digital-comics",
            format: "png"
          }

        },

        {
          name: "dc merchandise",
          href: "https://shop.dc.com/",
          img: {
            name: "buy-comics-merchandise",
            format: "png"
          }
        },
        {
          name: "print subscriptions",
          href: "https://www.dc.com/ComicShopLocator",
          img: {
            name: "buy-comics-subscriptions",
            format: "png"

          },
        },
        {
          name: "comic shop locator",
          href: "https://www.dc.com/subscriptions",
          img: {
            name: "buy-comics-shop-locator",
            format: "png"
          }
        },
        {
          name: "dc power visa",
          href: "https://www.dc.com/ComicShopLocator",
          img: {
            name: "buy-dc-power-visa",
            format: "svg"
          }

        },

      ],
    }
  },

  methods: {

    /* FUNZIONE GENERICA NON FUNZIONANTE */
    //dovrebbe creare un valido URL per l'src delle immagini
    /**
     * @param {string} fileName nome del file immagine        es: "pincopallo"
     * @param {.string} format formato del file               es: "png"
     */
    getImgUrl(fileName, format) {

      return new URL(`../assets/${fileName}.${format}`, import.meta.url);
    },

    mounted() {
    }
  }
}
</script>


<style scoped lang="scss">
@use "../styles/partials/variables" as *;

.top-bunner {
  background-color: $primary;
  color: $light;
  .list-group-item{
    flex-basis: calc(100% / 5);
  }

  a {
    color: $light;
  }
  
  .link-img{
    max-height: 70px;
    max-width: 70px;
    padding-right: $spacer_1;
  }
}

</style>