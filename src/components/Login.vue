<template>
  <div>
    UserName:
    <label>
      <input type="text" v-model="loginForm.username" placeholder="Please enter your username"/>
    </label>
    <br/>
    Password:
    <label>
      <input type="text" v-model="loginForm.password" placeholder="Please enter your password"/>
    </label>
    <br/>
    <button v-on:click="login">Login</button>
  </div>
</template>

<script>
export default {
  name: 'Login',
  data () {
    return {
      loginForm: {
        username: '',
        password: ''
      },
      responseResult: []
    }
  },
  methods: {
    login () {
      console.log('here')
      this.$axios.post('/login', {
        username: this.loginForm.username,
        password: this.loginForm.password
      }).then(successResult => {
        console.log('the')
        if (successResult.data.code === 200) {
          console.log('success')
          this.$router.replace({ path: '/index' })
        }
      }).catch(failureResult => {
        console.log(failureResult)
      })
    }
  }
}
</script>
