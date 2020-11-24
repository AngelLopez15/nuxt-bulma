<template>
  <div class="container">
    <div class="columns is-multiline">
      <div 
        class="column is-4"
        v-for="(item, index) in articulos" :key="index"
      >
        <h2 class="title is-size-3 has-text-centered">
          <nuxt-link :to="`/blog/${item.id}`">{{item.titulo}}</nuxt-link>
        </h2>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data(){
    return{
      articulos:[
        {id:1, titulo:'titulo 1'},
        {id:2, titulo:'titulo 2'},
        {id:3, titulo:'titulo 3'},
        {id:4, titulo:'titulo 4'},
        {id:5, titulo:'titulo 5'},
        {id:6, titulo:'titulo 6'},
      ]
    }
  }
}
</script>