<template>
  <div class="home">
    <JumboTron/>
  </div>
</template>
<script>
// @ is an alias to /src
// import HomeComponent from '@/components/HomeComponent.vue'
import JumboTron from '@/components/JumboTron.vue'

export default {
  name: 'HomeView',
  components: {
    JumboTron
  }
}
</script>
