<template>
    <div v-if="joke">
        <h2>{{ joke }}</h2>
        <small> joke id {{ $route.params.id }}</small>
    </div>
</template>

<script>
import axios from 'axios';
export default {

    data() {
        return {
            joke: {},
        }
    },

    async created() {
        const config = {
            headers: {
                Accept: "application/json"
            }
        };
        try {
            const res = await axios.get(`https://icanhazdadjoke.com/j/${this.$route.params.id}`, config);
            this.joke = res.data.joke;
            console.log(res)
        } catch (err) {
            console.log(err)
        }
    },
    head() {
        return {
            title: this.joke
        }
    }
}
</script>

<style scoped>
</style>