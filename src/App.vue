<!--******************
    APP TEMPLATE
***********************-->

<template>

<header>
  <TheNavbar></TheNavbar>
</header>
 

  <main>
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
import TopBunner from './components/TopBunner.vue';
import TheFooter from './components/TheFooter.vue';
import BottomBunner from './components/BottomBunner.vue';


export default {

  components: {
    TheNavbar,
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

*{
/*   border: 1px solid yellowgreen */
}

</style>