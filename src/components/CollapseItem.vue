<template >
  <b-container class="flex-col bordered mx-auto my-2 offset-lg-5">
    <div class="flex-row space-between">
    <div
      :class="visible ? null : 'collapsed'"
      :aria-expanded="visible ? 'true' : 'false'"
      aria-controls="collapse-4"
      @click="visible = !visible"
      class="flex-row"
    >
      {{id}} {{name}}
    <font-awesome-icon icon="fa-solid fa-arrow-down" color="black" class="adjust-vertical"/>
    </div> <!-- Name and down arrow icon -->
    <div class="flex-row"> <!-- Edit and Delete icons-->
      <font-awesome-icon icon="fa-solid fa-pencil" color="black" class="adjust-vertical" @click.stop=""/>
      <font-awesome-icon icon="fa-solid fa-trash" color="black" class="adjust-vertical" @click.stop="deleteContact(id)"/>
    </div>
    </div>
    <b-collapse id="collapse-4" v-model="visible" class="mt-2">
      <b-card>
          <p><b>Email: </b>{{email}}</p>
          <hr/>
          <p><b>Phone: </b>{{phone}}</p>
      </b-card>
    </b-collapse>
  </b-container>
</template>

<script>
import Vue from 'vue'
import { library } from '@fortawesome/fontawesome-svg-core'

import { faArrowDown, faTrash } from '@fortawesome/free-solid-svg-icons'

import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome'

import store from '@/store/store.js'

library.add(faArrowDown)
library.add(faTrash)

Vue.component('font-awesome-icon', FontAwesomeIcon)
export default {
  name: 'CollapseItem',
  components: {
    FontAwesomeIcon
  },
  data () {
    return {
      visible: false
    }
  },
  methods: {
    deleteContact: function (id) {
      const newStore = store.contacts.filter((element) => element.id !== id)
      store.contacts = newStore
      console.log(store.contacts)
    }
  },
  props: {
    name: String,
    email: String,
    phone: String,
    id: Number
  }
}
</script>

<style scoped>
.bordered{
    border: 1px solid #f5f5f5;
    padding: 10px;
    width: 80%;
    text-align: left;
}
.flex-row{
    display: flex;
    flex-direction: row;
    align-items: center;
}
.adjust-vertical{
    margin: -15px 5px;
}
.flex-col{
    display: flex;
    flex-direction: column;
}
.space-between{
    justify-content: space-between;
}
</style>
