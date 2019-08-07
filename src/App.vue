<template>
  <div>
    <Sidebar></Sidebar>
    <Search></Search> 
    <ListGifs></ListGifs>
  </div>
</template>

<script>
import Sidebar from './components/Sidebar.vue'
import Search from './components/Search.vue'
import ListGifs from './components/ListGifs.vue'


export default {
  name: 'app',
  components: {
   Sidebar,
   Search,
   ListGifs
  }
}

</script>
