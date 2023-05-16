<template>
<header>
    <nav className="flex sm:justify-center space-x-4">
      <ul>
        <li><NuxtLink to="/loginpage">Login</NuxtLink></li>
        <li><NuxtLink to="/registrationpage">Register</NuxtLink></li>
      </ul>
    </nav>
  </header>   
</template>
  
  <script>
  export default {
    name: 'NavBar'
  }
  </script>