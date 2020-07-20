<template>
  <div class="home">
    <Navbar />
    <Search />
  </div>
</template>

<script>
// @ is an alias to /src
import Navbar from '@/components/Navbar.vue'
import Search from '@/components/Search.vue'

export default {
  name: 'home',
  components: {
    Navbar, Search
  }
}
</script>
