<template>
  <div class="search">
    <div class="container">
    <form @submit.prevent="getApiInfo(query)">
      <input type="text" v-model="query" class="">
    </form>
    <div v-if="results">
      <div v-for="(result, key) in results" :key="key" >
        <img v-bind:src="result.links[0].href" />
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
   height: 400px;
 }
</style>
