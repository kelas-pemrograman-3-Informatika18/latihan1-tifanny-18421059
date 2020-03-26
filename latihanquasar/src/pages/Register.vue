<template>
    <q-page>
    Halaman Register
    <q-form
      @submit="onSubmit"
      @reset="onReset"
      class="q-gutter-md"
    >
      <q-input
        filled
        v-model="Name"
        label="Your Name *"
        lazy-rules
        :rules="[ val => val && val.length > 0 || 'Please type Name']"
      />

      <q-input
        filled
        v-model="Username"
        label="Your Username *"
        lazy-rules
        :rules="[val => val !== null && val.length > 0 || 'Please type your Username']"
      />
      <q-input
        filled
        type="Password"
        v-model="password"
        label="Your password *"
        lazy-rules
        :rules="[
          val => val !== null && val.length > 0 || 'Please type your password'
        ]"
      />
      <q-input
        filled
        type="Password"
        v-model="password"
        label="Confirm Your password *"
        lazy-rules
        :rules="[
          val => val !== null && val.length > 0 || 'Please Re-type your password'
        ]"
      />
      <div>
        <q-btn label="Submit" type="submit" color="primary"/>
        <q-btn label="Reset" type="reset" color="primary" flat class="q-ml-sm" />
      </div>
    </q-form>
    </q-page>
</template>
<script>
export default {
  data () {
    return {
      Name: null,
      Username: null,
      Password: null
    }
  },
  methods: {
    onSubmit () {
      console.log('Ini fungsi submit')
    },
    onReset () {
      console.log('ini fungsi reset')
    }
  }
}
</script>
