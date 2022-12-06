<!--******************
    APP TEMPLATE
***********************-->

<template>

  <TheNavbar></TheNavbar>


  <main>
    <ComicContainer></ComicContainer>
    <TopBunner></TopBunner>
  </main>

  <TheFooter></TheFooter>

  <BottomBunner></BottomBunner>
</template>


<!--******************
    APP SCRIPT
***********************-->

<script>

import TheNavbar from './components/TheNavbar.vue';
import ComicContainer from './components/ComicContainer.vue';
import TopBunner from './components/TopBunner.vue';
import TheFooter from './components/TheFooter.vue';
import BottomBunner from './components/BottomBunner.vue';


export default {

  components: {
    TheNavbar,
    ComicContainer,
    TopBunner,
    TheFooter,
    BottomBunner
  },

  data() {
    return {}
  },

}
</script>



<!--******************
    APP STYLE
***********************-->

<!-- non deve mai esservi lo scope nello style dell'App -->
<style lang="scss">
@use "./styles/general.scss" as *;

</style>