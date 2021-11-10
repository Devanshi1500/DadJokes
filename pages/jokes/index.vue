<template>
  <div class="m-10">
    <SearchJokes @search-text="searchText" />
    <Joke v-for="j of jokes" :key="j.id" :id="j.id" :joke="j.joke" />
    <pagination v-model="page" :records="33*20" :per-page="20" @paginate="paginate" class="font-light text-xl"/>
  </div>
</template>

<script>
import axios from 'axios';
import Pagination from 'vue-pagination-2';

export default {
  data() {
    return {
      jokes: [],
      page: 1,
      baseURL: this.$store.state.rootStore.baseURL,
      config: this.$store.state.rootStore.config
    }
  },
  components: {
    Pagination
  },
  methods: {
    async searchText(text) {
      try {
        const res = await axios.get(`${this.baseURL}/search?term=${text}`, this.config)
        this.jokes = res.data.results
      } catch (error) {
        console.log(error)
      }
    },
    async paginate(page) {
      try {
        const res = await axios.get(`${this.baseURL}/search?page=${page}`, this.config)
        this.jokes = res.data.results
      } catch (error) {
        console.log(error)
      }
    }
  },
  async created() {
    try {
      const res = await axios.get(`${this.baseURL}/search`, this.config)
      this.jokes = res.data.results
    } catch (error) {
      console.log(error)
    }
  },
  head() {
    return {
      title: 'DadJokes',
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
  .VuePagination nav ul {
    @apply flex;
  }
  .VuePagination nav ul li {
    @apply p-2;
  }
  .VuePagination .active {
    @apply font-bold;
  }
  .VuePagination__count {
    @apply text-sm;
  }
</style>