<template>
  <div>
    <h1>Register</h1>

    <input v-model="email" type="text" placeholder="Email"/>
    <input v-model="password" type="password" placeholder="Password" />
    <button @click="register">Register</button>
  </div>
</template>

<script>
import AuthenticationServices from '@/services/AuthenticationServices'


  export default {
    name: 'register',
    data(){
      return {
        email: '',
        password: ''
      }
    },
    methods: {
      async register(){
        await AuthenticationServices.register({
           email: this.email,
           password: this.password
        })
      }
    }
  }
</script>

<style lang="scss" scoped>

</style>