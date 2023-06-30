<template>
  <div class="container mx-auto px-4">
    <NavBar/>
    <App/>
    <p v-if="user">Hi {{ user.name }}</p>
  </div>
</template>

<script>
import axios from 'axios'

export default {
  data() {
    return {
      user: this.$auth.user,

    }
  },
  beforeCreate(){
    // get currently logged in user
    axios.get('http://127.0.0.1:8000/api/user').then(function(response){
        console.log(response)
    })
  },
  methods: {
    async logout() {
      await this.$auth.logout()
      this.$router.push('/login')
    },
  },
}
</script>
