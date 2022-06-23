<template>
  <div>
    <h2>Welcome to dad jokes {{ jokes.length }}</h2>
    <h3 v-if="jokes.length === 0">Loading...</h3>
    <joke v-for="joke of jokes" :joke="joke" />
  </div>
</template>

<script>

import axios from 'axios';
import joke from '../components/joke';

export default {
  head() {
    return {
      title: "Dad Jokes",
      meta: [
        {
          hid: "description",
          name: "description",
          content: "Best place for corny dad jokes"
        }
      ]
    };
  },
  data() {
    return {
      jokes: []
    }
  },
  components: {
    joke,
  },
  async created() {
    const config = {
      headers: {
        Accept: "application/json"
      }
    };
    try {
      const res = await axios.get('https://icanhazdadjoke.com/search', config);
      this.jokes = res.data.results;
    } catch (err) {
      console.log(err)
    }
  },
  methods: {
    loadJokes() {

    }
  }
};
</script>

<style scoped>
h2 {
  font-size: 40px;
  color: rgb(17, 80, 80);
  opacity: 0.2;
  margin-bottom: 20px;
}

h3 {
  color: rgb(17, 80, 80);
  opacity: 0.2;
  letter-spacing: 1px;
}
</style>