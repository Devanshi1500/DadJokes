<template>
  <div class="text-center">
    <h1 class="text-3xl font-semibold p-4">About DadJokes</h1>
    <p class="text-xl font-light pb-4">This is an app that displays corny dad jokes</p>
  </div>
</template>

<script>
export default {
  head() {
    return {
      title: 'About the app',
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: 'Best place for corny dad jokes'
        }
      ]
    }
  }
}
</script>

<style>

</style>