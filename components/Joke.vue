<template>
  <nuxt-link :to="'jokes/' + id">
    <div class="text-yellow-200 mb-10 font-extralight text-2xl">
      <p>{{ joke }}</p>
    </div>
  </nuxt-link>
</template>

<script>
export default {
  name: 'Joke',
  props: ['joke', 'id']
}
</script>

<style>

</style>