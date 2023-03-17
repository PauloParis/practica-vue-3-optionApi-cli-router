<template>
  <div class="about">
    <Titulo texto="Página de about"></Titulo>
    
  </div>
</template>

<script>
import Titulo from '../components/Titulo.vue';

export default {
  components: {
    Titulo
  },
  data() {
    return {
      
    }
  },
  methods: {
    
  }
}
</script>

<style>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}
</style>
