<script setup>
import { RouterLink, RouterView } from 'vue-router'
import 'bootstrap/dist/css/bootstrap.css'
</script>

<template>
<div class="container mt-5">
  11111
  <button @click.prevent="testMethod()" class="btn btn-outline-primary">Кнопка</button>
  <template v-if="data">
    <div v-for="post in data">
      {{post}}
    </div>

  </template>
</div>
</template>

<script>
import axios from 'axios'
import 'bootstrap/dist/js/bootstrap'

export default {
  name: 'App',
  data(){
    return{
      data: {

      }
    }
  },
  mounted() {
    this.testGet()
  },
  methods: {
    testMethod(){
      axios.get('https://jsonplaceholder.typicode.com/posts')
          .then(res=>{
            this.data = res.data
          })
    },
    testGet(){
      axios.get('https://api.alexeybychkovski.site/api/get')
          .then(res => {
            console.log(res)
          })
    }
  }
}

</script>
<style scoped>

</style>
