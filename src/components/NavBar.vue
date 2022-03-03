<template style="background-color:#000;">
<div>
  <b-navbar toggleable="lg" type="dark" variant="dark">
    <router-link to="/" class="no-underline">
          <b-navbar-brand href="/">Contact Manager</b-navbar-brand>
    </router-link>
    <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

    <b-collapse id="nav-collapse" is-nav>
      <!-- Right aligned nav items -->
      <b-navbar-nav class="pull-right ms-auto">
        <router-link to="/" class="no-underline">
          <b-nav-item href="/"> <font-awesome-icon icon="fa-solid fa-house" color="white"/> Home</b-nav-item>
        </router-link>
        <router-link to="/add" class="no-underline">
          <b-nav-item href="/add"> <font-awesome-icon icon="fa-solid fa-pencil" color="white"/> Add</b-nav-item>
        </router-link>
        <router-link to="/about" class="no-underline">
        <b-nav-item href="/about"> <font-awesome-icon icon="fa-solid fa-question" color="white"/> About</b-nav-item>
        </router-link>
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
.no-underline{
  text-decoration:none;
}
</style>
