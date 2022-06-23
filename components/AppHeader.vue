<template>

    <nav>

        <nuxt-link to="/">Home</nuxt-link>
        <nuxt-link to="/about">About </nuxt-link>
        <nuxt-link to="/jokes">Jokes </nuxt-link>

    </nav>

</template>

<script>

</script>

<style scoped>
nav {
    height: 60px;
    background-color: #F4F4F4;
    display: flex;
    justify-content: flex-end;
    align-items: center;
    padding-right: 10px;
    margin-bottom: 30px;
}

nav a {
    padding-left: 20px;
    font-weight: bold;


}
</style>