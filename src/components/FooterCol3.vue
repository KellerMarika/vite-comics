<template>

  <div v-for="(list) in linksLists">
    <h4 class="text-uppercase text-light pt-3">{{list.title}}</h4>
    <ul class="p-0">
      <li  v-for ="(link) in list.links"  class="list-group-item">
        <a :href="link.href">{{link.name}}</a>
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
}
</script>
  
<style scoped lang="scss">
</style>