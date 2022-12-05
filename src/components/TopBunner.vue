<template>
  <article class="top-bunner py_l">
    <div class="container">
      <!--   <img src="../assets/buy-comics-digital-comics.png" alt=""> -->
      <ul class="list-group-flush d-flex justify-content-around">
        <li class="list-group-item"
            v-for="(link, i) in bunnerLinks">
          <a target="_blank" class="d-flex align-items-center" :href="link.href">

            <img :src="getImgUrl(`../assets/`, link.imgName, `.png`)" :alt="link.imgName">

            <h6 class="text-uppercase p-3 small">{{ link.name }}</h6>
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
          imgName: "buy-comics-digital-comics",
          href: "https://www.dcuniverseinfinite.com/",
        },
        {
          name: "dc merchandise",
          imgName: "buy-comics-merchandise",
          href: "https://shop.dc.com/",
        },
        {
          name: "print subscriptions",
          imgName: "buy-comics-shop-locator",
          href: "https://www.dc.com/subscriptions",
        },
        {
          name: "comic shop locator",
          imgName: "buy-comics-subscriptions",
          href: "https://www.dc.com/ComicShopLocator",
        },

      ],
    }
  },
  methods: {

    getImgUrl(relativeURL, fileName, format) {
      let imgURL = relativeURL + fileName + format;
      console.log("imgURL", imgURL);
      return new URL(`${imgURL}`, import.meta.url);
      /*   return new URL(`${relativeURL}${fileName}.${format}`, import.meta.url); */

    },
  },
  mounted() {
    /*     console.log(this.getImgUrl("../assets/", this.bunnerLinks[1].imgName, ".png")); */
  }
}
</script>

<style scoped lang="scss">
@use "../styles/partials/variables" as *;

* {
  border: 1px solid rgb(253, 249, 19);
}

.top-bunner {
  background-color: $primary;
  color: $light;

  a {
    color: $light;
  }
}
</style>