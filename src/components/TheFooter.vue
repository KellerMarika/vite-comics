<template>
  <footer class="bg-footer ">
    <div class="container ">
      <div class="row">
        <div class="col-4 py_m">
          <div class="row row-cols-3">
            <FooterCol1 class="col"></FooterCol1>
            <FooterCol2 class="col"></FooterCol2>
            <FooterCol3 class="col"></FooterCol3>
          </div>

        </div>
        <div class="col-6 offset-2 footer-dc-logo"></div>
      </div>
    </div>
  </footer>
</template>

<script>
import FooterCol1 from './FooterCol1.vue';
import FooterCol2 from './FooterCol2.vue';
import FooterCol3 from './FooterCol3.vue';

export default {
  components: {
    FooterCol1,
    FooterCol2,
    FooterCol3,
  },
  data() {
    return {

    }
  }

}
</script>

<style scoped lang="scss">
.bg-footer {
  background-image: url(../assets/footer-bg.jpg);
  background-repeat: no-repeat;
  background-size: cover;
}

.footer-dc-logo {
  background-image: url(/dc-logo-bg.png);
  background-repeat: no-repeat;
  background-size: cover;
  background-position: center;
}
</style>

<!-- style senza scope  _____________________________________________________ -->

<style lang="scss">
@use "../styles/partials/variables" as *;

.bg-footer {
  a {
    color: $secondary_light;
  }
}
</style>