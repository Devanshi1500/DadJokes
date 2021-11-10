<template>
  <div class="m-10 p-5">
    <nuxt-link to='/jokes' class="hover:text-gray-200">
      Back to Jokes
    </nuxt-link>
    <h3 class="font-semibold text-2xl mt-2">{{ joke }}</h3>
  </div>
</template>

<script>
import axios from 'axios';

export default {
  data() {
    return {
      joke: '',
      baseURL: this.$store.state.rootStore.baseURL,
      config: this.$store.state.rootStore.config
    }
  },
  async created() {
    try {
      const res = await axios.get(`${this.baseURL}/j/${this.$route.params.id}`, this.config)
      this.joke = res.data.joke
    } catch (error) {
      console.log(error)
    }
  },
}
</script>

<style>

</style>