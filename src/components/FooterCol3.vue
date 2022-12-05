<template>

  <div v-for="(list) in linksLists">
    <h3 class="text-uppercase text-light pt-3">{{list.title}}</h3>
    <ul class=" m-0 p-0">
      <li class="list-group-item">
        <a v-for ="(link) in list.links" :href="link.href">{{link.name}}</a>
      </li>
    </ul>
  </div>

</template>
  
<script>
import { col3_Lists } from '../composables/footerLinks';
export default {
  data(){
    return{
      linksLists:col3_Lists
    }
  },
  mounted(){
    console.log(this.linksLists)
  }

}
</script>
  
<style scoped lang="scss">
* {
  border: 1px solid rgb(248, 52, 3);
}
</style>