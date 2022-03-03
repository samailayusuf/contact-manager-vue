<template>
  <b-navbar toggleable="lg" type="dark" variant="dark" class="flex center">
      <p class="center flex">&copy; {{new Date().getFullYear() }}.  Yusuf Samaila</p>
  </b-navbar>
</template>

<script>
export default {
  name: 'FooterComponent'
}
</script>

<style>
    .flex{
        display:flex;
        justify-content:center;
        align-items: center;
    }
    .center{
        color:white;
        text-align:center;
    }
</style>
