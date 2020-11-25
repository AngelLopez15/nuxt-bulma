<template>
  <div class="container">
    <!-- <div class="columns is-multiline">
      <div 
        class="column is-4"
        v-for="(item, index) in articulos" :key="index"
      >
        <h2 class="title is-size-3 has-text-centered">
          <nuxt-link :to="`/blog/${item.id}`">{{item.titulo}}</nuxt-link>
        </h2>
      </div>
    </div> -->
    <div class="columns is-multiline">

      <div class="card" v-for="(item, index) in articulos" :key="index" >
        <div class="card-content">
          <div class="media">
            <div class="media-content">
              <nuxt-link :to="`blog/${item.id}`">
                <h1 class="title is-4">{{item.title}}</h1>
              </nuxt-link>
              <p class="subtitle is-6">{{item.body}}</p>
            </div>
          </div>
        </div>
      </div>

    </div>

  </div>
</template>

<script>
import axios from 'axios'
// https://jsonplaceholder.typicode.com/posts?_limit=10
export default {
  data(){
    return{
      articulos:[
        // {id:1, titulo:'titulo 1'},
        // {id:2, titulo:'titulo 2'},
        // {id:3, titulo:'titulo 3'},
        // {id:4, titulo:'titulo 4'},
        // {id:5, titulo:'titulo 5'},
        // {id:6, titulo:'titulo 6'},
      ]
    }
  },
  async created(){
    try {
      const res = await axios.get('https://jsonplaceholder.typicode.com/posts?_limit=10')
      // console.log(res.data)
      this.articulos = res.data;
    } catch (error) {
      console.log(error)
    }
  }
}
</script>