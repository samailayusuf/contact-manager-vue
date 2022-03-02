<template>
<div>
  <b-container>
    <h1 class="pull-left">About us</h1>
    <p class="pull-left size-22">This is an app created to manage contacts. It could be seen and used as a backup for your contacts
      <small class="small">....Version 1.0.0</small></p>
  </b-container>
</div>
</template>

<script>
// import NavBar from '@/components/NavBar.vue'
export default {
  name: 'AboutView',
  components: {
  }
}
</script>

<style scoped>
.pull-left{
  text-align: left;
  margin-top: 20px;
}
.size-22{
  font-size:22px;
  font-weight:normal;
}
.small{
  font-size:14px;
}
</style>
