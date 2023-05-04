<template>
<div>
    <h1>Registration</h1>
    <form action=""  method="POST" @submit="createAccount">
        <label for="FullName">Name:</label>
        <input id="fullname" type="text" placeholder="Full Name" name="FullName">
        <br>
        <label for="Email">Email</label>
        <input id="email" type="email" placeholder="exampl@gmail.com" name="Email">
        <br>
        <label for="Password">Password</label>
        <input id="password" type="password" name="Password"/>
        <br>
        <label for="ConfirmPassword">Confirm Password</label>
        <input id="confirmpassword" type="password" name="ConfirmPassword">
        <br>
        <input id="submit" type="submit" value="Submit">
    </form>
</div>

</template>

<script>
import axios, {isCancel, AxiosError} from 'axios';
export default {
    name: 'RegistrationPage',
    mounted() {
// code here runs when a component is mounted !!

  },
    methods: {  
    createAccount(e) {
      e.preventDefault()
      let firstName = document.getElementById('fullname');
      let email = document.getElementById('email');
      let password = document.getElementById('password');
      let confirmpassword = document.getElementById('confirmpassword');

      const submitAccountInfo = require('axios');

      axios.post('http://127.0.0.1:8000/api/createuser',{
        name: firstName.value,
        email: email.value,
        password: password.value,
        confirmpassword: confirmpassword.value
    })
  .then(function (response) {
    console.log(response);
  })
  .catch(function (error) {
    console.log(error);
  });
    }
  },
  }
</script>