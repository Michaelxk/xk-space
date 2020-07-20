<template>
  <div class="search">
    <div class="container">
    <form @submit.prevent="getApiInfo(query)">
      <input type="text" v-model="query" class="form-control" placeholder="Coloca el nombre de un planeta...">
      <button class="btn-primary mt-2">Busca tu Planeta</button>
    </form>
    <div v-if="results" class="result mt-5">
      <div v-for="(result, key) in results" :key="key" >
        <img v-bind:src="result.links[0].href" />
        <h5></h5>
      </div>
    </div>
    </div>
  </div>
</template>

<script>
import axios from 'axios'

export default {
  name: 'Search',
  data () {
    return {
      query: '',
      results: ''
    }
  },
  methods: {
    getApiInfo (query) {
      axios.get('https://images-api.nasa.gov/search?q=' + query + '&media_type=image')
        .then(response => {
          console.log(response.data.collection.items)
          this.results = response.data.collection.items
        })
    }
  }
}
</script>
<style scoped lang="scss">
img {
  width: 400px;
  height: 300px;
  max-width: 100%;
 }
 .search {
   margin-top: 5em;
 }
 .form-control {
   width: 33vw;
 }
.btn-primary {
  width: 30em;
  text-transform: uppercase;
  border: none;
  border-radius: 1.5em;
  padding: 5px;
}
.result {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  justify-content: center;
  grid-gap: 5px;
}
</style>
