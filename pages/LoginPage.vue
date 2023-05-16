<template>
  <div>
    <NavBar />
    <h1>Login</h1>
    <form action="" method="POST" @submit.prevent="login">
      <label for="Email">Email</label>
      <input id="email" type="email" placeholder="exampl@gmail.com" name="Email">
      <br>
      <label for="Password">Password</label>
      <input id="password" type="password" name="Password" />
      <br>
      <input id="submit" type="submit" value="Submit">
    </form>
  </div>
</template>
    
<script>
// pages/login.vue
import axios, { isCancel, AxiosError } from 'axios';
export default {
  name: 'LoginPage',
  data() {
    return {
      email: '',
      password: '',
    }
  },
  methods: {
    async login() {
      let email = document.getElementById('email');
      let password = document.getElementById('password');

   
      
      axios.get('http://localhost:8000/sanctum/csrf-cookie',{ withCredentials: true }).then(response => {
        
        return axios.post('http://localhost:8000/api/login',{
          email: email.value,
          password: password.value
        },{ withCredentials: true })
        }).then(response =>{

          if(response.status == 200){
            this.$router.push('/');
            console.log(this.$auth);

          }
        })
        .catch(function (error) {
         console.log(error);
      });
    },

    
  },
}
</script>