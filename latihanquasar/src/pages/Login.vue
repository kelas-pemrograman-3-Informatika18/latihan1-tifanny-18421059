<template>
    <q-page class="bg-green-2">
      <div class="row">
        <q-card class="fixed-center col-md-4 col-xs-12 bg-white" flat>
          login page
    <q-form
      @submit="onSubmit"
      @reset="onReset"
      class="q-gutter-md"
    >
      <q-input
        filled
        v-model="username"
        label="Your Username *"
        lazy-rules
        :rules="[ val => val && val.length > 0 || 'Please type username']"
      />

      <q-input
        filled
        type="password"
        v-model="password"
        label="Your password *"
        lazy-rules
        :rules="[
          val => val !== null && val.length > 0 || 'Please type your password'
        ]"
      />
      <div>
        <q-btn label="Login" type="submit" color="primary"/>
        <q-btn label="Reset" type="reset" color="primary" flat class="q-ml-sm" />
      </div>
    </q-form>
    </q-card>
      </div>
    </q-page>
</template>
<script>
export default {
  data () {
    return {
      username: null,
      password: null
    }
  },
  methods: {
    onSubmit () {
      if (this.username === 'tifanny' && this.password === '112233') {
        this.$q.notify({
          type: 'positive',
          message: 'Congratulation your login allready succesful'
        })
        this.$router.push('/home')
      } else {
        this.$q.notify({
          type: 'negative',
          message: 'Sorry please correct your password or username'
        })
      }
    },
    onReset () {
      this.username = null
      this.password = null
    }
  }
}
</script>
