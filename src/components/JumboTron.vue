<template>
<b-container>
  <b-jumbotron class="gray">
      <h2 class="text-center mt-5">Contact Manager</h2>
    <p class="large">This is a portfolio project to showcase knowledge of:</p>
    <ol type="i">
     <li>Vue Components and Templates</li>
     <li>Vue Router</li>
     <li>Components state management</li>
     <li>Using store for global state management</li>
     <li>Making asynchronous call to JSON placeholder API</li>
    </ol>
  </b-jumbotron>
  </b-container>
</template>

<script>
export default {
  name: 'JumboTron'
}
</script>

<style>
 .gray{
     background-color: #f5f5f5;
     text-align: left;
     margin:20px;
     border-radius:5px;
     padding: 20px;
 }
 .large{
     font-size:18px;
 }
</style>
