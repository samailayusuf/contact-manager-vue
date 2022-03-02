<template style="background-color:#000;">
<div>
  <b-navbar toggleable="lg" type="dark" variant="dark">
    <b-navbar-brand href="#">NavBar</b-navbar-brand>

    <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

    <b-collapse id="nav-collapse" is-nav>
      <!-- Right aligned nav items -->
      <b-navbar-nav class="pull-right ms-auto">
        <b-nav-item href="#"> <font-awesome-icon icon="fa-solid fa-house" color="white"/> Home</b-nav-item>
        <b-nav-item href="#"> <font-awesome-icon icon="fa-solid fa-pencil" color="white"/> Add</b-nav-item>
        <b-nav-item href="#"> <font-awesome-icon icon="fa-solid fa-question" color="white"/> About</b-nav-item>
        <b-nav-item href="#" disabled>Disabled</b-nav-item>
      </b-navbar-nav>
    </b-collapse>
  </b-navbar>
</div>
</template>

<script>
import Vue from 'vue'
import { library } from '@fortawesome/fontawesome-svg-core'

import { faHatWizard } from '@fortawesome/free-solid-svg-icons'

import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome'

library.add(faHatWizard)

Vue.component('font-awesome-icon', FontAwesomeIcon)

export default {
  name: 'NavBar',
  components: {
    FontAwesomeIcon
  }
}
</script>

<style>
.right{
    text-align: right;
    margin-right: 5px;
    position: relative;
    right: 10px;
}
.right{
    display:flex;
    justify-content: flex-end;
}
</style>
