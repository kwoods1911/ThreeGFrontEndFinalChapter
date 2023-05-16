<template>
  <div>
    <NavBar/>
    <App/>
    <!-- <p>Hi {{ user.name }}</p> -->
    <a href="#" @click.prevent="logout">Logout</a>
  </div>
</template>

<script>
import axios from 'axios'

export default {
  data() {
    return {
      user: '',
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
