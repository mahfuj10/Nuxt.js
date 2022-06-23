<template>
    <nuxt-link :to="'/' + joke.id">
        <div class="joke">
            <h5>{{ joke.joke }}</h5>
        </div>
    </nuxt-link>
</template>

<script>

export default {
    name: 'joke',
    props: {
        joke: Object
    }
}
</script>

<style scoped>
.joke {
    padding: 8px;
    border: 1px solid #CFDCDC;
    margin-bottom: 20px;
    cursor: pointer;
}
</style>