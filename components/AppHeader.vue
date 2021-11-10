<template>
  <header class="flex flex-col text-center mb-10">
    <h1 class="text-5xl text-yellow-500 m-10 font-bold">Dad Jokes</h1>
    <ul class="grid grid-cols-3 justify-items-center">
      <li class="m-5 text-xl font-light">
        <nuxt-link to='/'>Home</nuxt-link>
      </li>
      <li class="m-5 text-xl font-light">
        <nuxt-link to='/about'>About</nuxt-link>
      </li>
      <li class="m-5 text-xl font-light">
        <nuxt-link to='/jokes'>Jokes</nuxt-link>
      </li>
    </ul>
  </header>
</template>

<script>
export default {
  name: 'AppHeader'
}
</script>

<style>
</style>