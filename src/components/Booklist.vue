<template>
  <div class="">
    <h2>Booklist</h2>
    <ul>
      <li v-for="book in books">{{book.name}}</li>
    </ul>
  </div>

</template>

<script>
import Vue from 'vue'
import axios from 'axios'
import VueAxios from 'vue-axios'

Vue.use(VueAxios, axios)


export default {
  name: "Booklist",
  data() {
    return{
        books: []
    }

  },
  beforeMount(){
    Vue.axios.get("http://localhost:3000/books.json").then((response) => {
      this.books = response.data
  })
}
}
</script>

<style scoped>

</style>
