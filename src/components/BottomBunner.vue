<template>
  <article class="bg-secondary">
    <div class="container d-flex align-items-center py_m">

      <button class="login-btn text-uppercase text-light bg-transparent border-primary p-2"> sing-up now!</button>

      <div class="flex-fill d-flex align-items-center justify-content-end">
        <h4 class="text-uppercase text-primary m-0">follow Us</h4>
        <ul class=" d-flex justify-content-end text-uppercase m-0">

          <li class="list-group-item"
              v-for="(link) in  socialLinks">
            <a target="_blank" class="h-100 p-2"
                :href="link.href">
              <img :src="`/${link.name}.${link.format}`" :alt="(link.name)">
            </a>
          </li>
        </ul>
      </div>

    </div>
  </article>
</template>
  
<script>
export default {
  data() {
    return {
      navLogoImg: {
        name: "dc-logo"
      },

      socialLinks: [
        {
          name: "footer-facebook",
          href: "/",
          format: "png"
        },
        {
          name: "footer-periscope",
          href: "/",
          format: "png"
        },
        {
          name: "footer-pinterest",
          href: "/",
          format: "png"
        },
        {
          name: "footer-twitter",
          href: "/",
          format: "png"

        },
        {
          name: "footer-youtube",
          href: "/",
          format: "png"

        }
      ],
    }
  },
  methods: {

    getImgUrl(fileName, format) {

      return new URL(`/${fileName}.${format}`, import.meta.url);
    },
  }
}
</script>
  
<style scoped lang="scss">
@use "../styles/partials/variables" as *;

.login-btn {
  border: 2px solid $primary;
}

</style>