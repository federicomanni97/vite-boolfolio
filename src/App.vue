<template>
  <div>
    <h1>ciao</h1>
  </div>
  <AppHeader/>
  <!-- router view caricherà le pagine richieste -->
  <router-view></router-view>
</template>

<script>

import axios from 'axios';
import { store } from './store'
import { RouterView } from 'vue-router';
import AppHeader from './components/AppHeader.vue';
export default {
  name: 'App', 
  components: { 
    RouterView,
    AppHeader 
  },
  data () {
    return {
      store, 
      projects: [],
    }
  },
  methods: {
    
  }, 
  mounted(){
  
  }
}
</script>

<style lang="scss" scoped>
@use "./assets/styles/partials/variables.scss" as *;

h1{
  color: $font-color;
}

</style>./store