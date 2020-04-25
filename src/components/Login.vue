<template>
  <div>
    UserName:<input type="text" v-model="loginForm.username" placeholder="Please enter your username"/>
    <br/>
    Password:<input type="text" v-model="loginForm.password" placeholder="Please enter your password"/>
    <br/>
    <button v-on:click="login">Login</button>
  </div>
</template>

<script>
  export default {
    name:'Login',
    data(){
      return {
        loginForm:{
          username:'',
          password:''
        },
        responseResult:[]
      }
    },
  }
</script>
