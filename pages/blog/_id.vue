<template>
  <div class="container">
    <h1>Articulo id:{{$route.params.id}}</h1>

    <div class="card">
      <div class="card-content">
        <div class="media">
          <div class="media-content">
            <h1 class="title is-4">{{articulo.title}}</h1>
            <p class="tag is-primary">{{articulo.userId}}</p>
            <p class="subtitle is-6">{{articulo.body}}</p>
            <nuxt-link to="/blog" class="button is-ghost">Atras</nuxt-link>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import axios from 'axios'

export default {
  data(){
    return{
      articulo:''
    }
  },
  async created(){
    try {
      const res = await axios.get(`https://jsonplaceholder.typicode.com/posts/${this.$route.params.id}`)
      this.articulo = res.data
    } catch (error) {
      console.log(error)
    }
  }  
}
</script>