<template>
  <div>
    <Sidebar></Sidebar>
    <AdvancedSearch></AdvancedSearch> 
  </div>
</template>

<script>
import Sidebar from './components/Sidebar.vue'
import AdvancedSearch from './components/AdvancedSearch.vue'

export default {
  name: 'app',
  components: {
   Sidebar,
   AdvancedSearch
  }
}
</script>
