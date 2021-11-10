<template>
  <div class="flex items-center m-10 p-10">
    <img src="../assets/gifs/dad.gif" class="h-60 w-80" />
    <div>
      <h2 class="font-light text-5xl text-yellow-200 text-center">
        Want to hear a joke?
      </h2>
      <p class="p-4 mx-10 font-extralight text-2xl">{{ joke }}</p>
    </div>
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
  head() {
    return {
      title: 'Welcome to dadjokes',
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: 'Best place for corny dad jokes'
        }
      ]
    }
  },
  mounted() {
    window.setInterval(() => {
      this.getADadJoke()
    }, 5000)
  },
  methods: {
    async getADadJoke() {
      try {
        const res = await axios.get(`${this.baseURL}`, this.config)
        this.joke = res.data.joke
      } catch (error) {
        console.log(error)
      }
    }
  }
}
</script>
