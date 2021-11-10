<template>
  <form @submit.prevent="OnSubmit()" class="mb-10">
    <input type="text" v-model="text" placeholder="Try 'hipster'" class="rounded-2xl pl-5 border-white border-4 text-black text-xl font-light">
    <input type="submit" value="Search" class="bg-gray-800 text-white border p-1 pr-5 pl-5 rounded-3xl border-white">
  </form>
</template>

<script>
export default {
  name: 'SearchJokes',
  data() {
    return {
      text: ''
    }
  },
  methods: {
    OnSubmit() {
      this.$emit('search-text', this.text)
      this.text = ''
    }
  }
}
</script>

<style>

</style>