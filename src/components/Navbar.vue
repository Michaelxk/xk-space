<template>
  <div class="navbar-content">
   <nav class="navbar-light bg-primary">
     <div class="container">
        <i class="fas fa-rocket"></i>
        <a class="navbar-brand" href="#">XK-Space</a>
     </div>
    </nav>
  </div>
</template>
<script>
export default {
  name: 'Navbar',
  data () {
    return {}
  }
}
</script>
<style scoped>
.navbar-brand {
  color: #fff;
  font-size: 1.5em;
  margin-left: .5em;
}
.fa-rocket {
  font-size: 1.5em;
  color: #fff;
}
</style>
