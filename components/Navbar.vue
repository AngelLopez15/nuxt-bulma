<template>
  <nav class="navbar-invalsa">
    <div>
      Logo
    </div>
    
    <ul class="navbar-invalsa-list">
      <li
        v-for="(item, index) in paginas" :key="index"
      >
        {{item.titulo}}
      </li>
    </ul>
    
  </nav>
</template>

<script>
export default {
  data(){
    return{
      paginas:[
        {titulo:'pagina1'},
        {titulo:'pagina2'},
        {titulo:'pagina3'},
        {titulo:'pagina4'},
        {titulo:'pagina5'}
      ]
    }
  }
}
</script>

<style>
  .navbar-invalsa{
    display: flex;
    background: #cecece;
    justify-content: space-between;
    padding: 1rem;
    margin-bottom: 2.5rem;
  }

  .navbar-invalsa-list{
    display: flex;
    width: 50%;
    justify-content: space-evenly;
  }
</style>