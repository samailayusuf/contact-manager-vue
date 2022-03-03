<template>
  <div class="home">
    <JumboTron/>
    <div v-for="contact in contacts" :key="contact.id">
      <CollapseItem :name="contact.name" :email="contact.email" :phone="contact.phone" :id="contact.id"/>
    </div>
  </div>
</template>
<script>
// @ is an alias to /src
// import HomeComponent from '@/components/HomeComponent.vue'
import JumboTron from '@/components/JumboTron.vue'
import store from '@/store/store.js'
import axios from 'axios'
import CollapseItem from '@/components/CollapseItem'

export default {
  name: 'HomeView',
  components: {
    JumboTron,
    CollapseItem
  },
  data () {
    return {
      visible: true
    }
  },
  computed: {
    contacts () {
      return store.contacts
    }
  },
  mounted () {
    axios.get('https://jsonplaceholder.typicode.com/users')
      .then((response) => {
        if (store.contacts.length < 1) {
          store.contacts = response.data
          this.contacts = store.contacts
          console.log(response.data)
        }
      })
      .catch(err => console.log(err))
    this.$root.$on('bv::collapse::state', (collapseId, isJustShown) => {
      // console.log('collapseId:', collapseId)
      // console.log('isJustShown:', isJustShown)
    })
  }
}
</script>

<style scoped>
.bordered{
  border: 1px solid #abc;
}
</style>
