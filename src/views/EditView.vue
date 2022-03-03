<template style="background-color:#000;">
<b-container>
 <div>{{$route.params.id}}</div>
    <b-form @submit="onSubmit" class="pull-left">
        <h5 style="padding:20px;background-color:#F0F0F0;">Edit Contact</h5>
        <b-form-group id="input-group-2" label="Your Name:" label-for="input-2">
        <b-form-input
          id="input-2"
          v-model="form.name"
          placeholder="Enter name"
          required
        ></b-form-input>
      </b-form-group>
      <b-form-group
        id="input-group-1"
        label="Email address:"
        label-for="input-1"
      >
        <b-form-input
          id="input-1"
          v-model="form.email"
          type="email"
          placeholder="Enter email"
          required
        ></b-form-input>
      </b-form-group>

      <b-form-group id="input-group-2" label="Your Name:" label-for="input-2">
        <b-form-input
          id="input-2"
          v-model="form.phone"
          placeholder="Enter Phone"
          required
        ></b-form-input>
      </b-form-group>

          <b-form-group>
          <div class="full">
              <b-button block  type="submit" variant="dark" class="full" :disabled="!form.name || !form.email || !form.phone">Edit </b-button>
          </div>
          </b-form-group>
    </b-form>
  </b-container> <!-- End of wrapper-->
</template>

<script>
import store from '@/store/store.js'
export default {
  data () {
    return {
      form: {
        name: '',
        email: '',
        phone: ''
      }
    }
  },
  methods: {
    onSubmit (event) {
      event.preventDefault()
      // alert(JSON.stringify(this.form))
      const contact = store.contacts[this.$route.params.id - 1]
      contact.name = this.form.name
      contact.email = this.form.email
      contact.phone = this.form.phone
      this.$router.push('/')
    }
  },
  mounted () {
    const selectedContact = store.contacts[this.$route.params.id - 1]
    console.log(selectedContact)
    this.form.name = selectedContact.name
    this.form.email = selectedContact.email
    this.form.phone = selectedContact.phone
  }
}
</script>
<style>
.pull-left{
    text-align: left;
    padding: 20px;
}
.full{
    width: 100%;
    margin: 5px 0px;
}
</style>
