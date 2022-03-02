<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <b-button variant="success">Hello there</b-button>
    <HomeComponent msg="Welcome to Your Vue.js App"/>
  </div>
</template>

<script>
// @ is an alias to /src
import HomeComponent from '@/components/HomeComponent.vue'

export default {
  name: 'HomeView',
  components: {
    HomeComponent
  }
}
</script>
