<template>
  <div class="bg-dark">
    <AppHeader/>
  </div>
  
  <!-- router view caricherà le pagine richieste -->
  <router-view></router-view>
  <FooterComponent/>
</template>

<script>

import axios from 'axios';
import { store } from './store'
import { RouterView } from 'vue-router';
import AppHeader from './components/AppHeader.vue';
import FooterComponent from './components/FooterComponent.vue';
export default {
  name: 'App', 
  components: { 
    RouterView,
    AppHeader,
    FooterComponent
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