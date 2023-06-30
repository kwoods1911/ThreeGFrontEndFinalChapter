<template>
<header>
    <!-- <nav className="flex sm:justify-center space-x-4">
      <ul>
        <li><NuxtLink to="/loginpage">Login</NuxtLink></li>
        <li><NuxtLink to="/registrationpage">Register</NuxtLink></li>
        <li><a href="#" @click.prevent="logout">Logout</a></li>
      </ul>
    </nav> -->

<ul class="flex border-b">

  <li class="-mb-px mr-1">
      <NuxtLink class="bg-white inline-block border-l border-t border-r rounded-t py-2 px-4 text-blue-700 font-semibold" to="/">Home</NuxtLink>
  </li>

  <li class="mr-1">
    <NuxtLink class="bg-white inline-block border-l border-t border-r rounded-t py-2 px-4 text-blue-700 font-semibold" to="/loginpage">Login</NuxtLink>
  </li>

  <li class="mr-1">
    <NuxtLink class="bg-white inline-block border-l border-t border-r rounded-t py-2 px-4 text-blue-700 font-semibold" to="/registrationpage">Register</NuxtLink>
  </li>
  <li class="mr-1">
    <NuxtLink class="bg-white inline-block border-l border-t border-r rounded-t py-2 px-4 text-blue-700 font-semibold" to="#">Login Out</NuxtLink>
  </li>
  
</ul>
  </header>   
</template>
  
  <script>
  export default {
    name: 'NavBar'
  }
  </script>