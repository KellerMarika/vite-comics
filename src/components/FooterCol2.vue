<template>

  <div v-for="(list) in linksLists">
    <h3 class="text-uppercase text-light pt-3">{{list.title}}</h3>
    <ul class=" p-0">
      <li  v-for="(link) in list.links" class="list-group-item">
        <a :href="link.href">{{link.name}}</a>
      </li>
    </ul>
  </div>

</template>
  
<script>
import { col2_Lists } from '../composables/footerLinks';
export default {
  data(){
    return{
      linksLists:col2_Lists
    }
  },
}
</script>
  
<style scoped lang="scss">
</style>