<template>

  <article class="jumbotron"></article>

  <article class="cards-container py_l">
    <div class="container text-center position-relative">

      <h1 class="cards-title text-uppercase bg-primary py-2 px-4 position-absolute fs-3"> current series </h1>

      <div class="row row-cols-6">

        <div class="col"
            v-for="(comic) in comics">

          <div class="dc-card text-start">

            <div class="dc-card-img">
              <img class="img-fluid"
                  :src="comic.thumb"
                  :alt="comic.series">
            </div>

            <h6 class="text-uppercase small py-3">{{ comic.series }}</h6>
          </div>
        </div>
      </div>

      <button class="btn btn-primary text-light text-uppercase rounded-0 fw-bold py-2 px-5">load more</button>
    </div>
  </article>
</template>

<script>
/* import {} from '../composables/dc-comics.json' */
import * as comicsList from "../composables/dc-comics.json"
export default {
  data() {
    return {
      comics: comicsList.default
    }
  },
  methods: {
  },
  mounted() {
  }
}

</script>

<style scoped lang="scss">
@use "../styles/partials/variables" as *;





.jumbotron {
  background-image: url(../assets/jumbotron.jpg);
  background-repeat: no-repeat;
  background-size: cover;
  background-position: top;
  height: 500px;

}

.cards-container {
  background-color: $dark;
  color: $light;

  .cards-title {
    top: -80px;
  }

  .dc-card-img {
    aspect-ratio: 1/1;
    overflow: hidden;
  }
}
</style>