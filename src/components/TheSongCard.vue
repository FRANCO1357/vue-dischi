<template>
        <figure>
            <img :src="poster" alt="title">
            <h4>{{ title }}</h4>
            <p>{{ author }}</p>
            <p>{{ year }}</p>
        </figure>
</template>

<script>
export default{
    name: 'TheSongCard',
    props: {
        poster: String,
        title: String,
        author: String,
        year: String,
    }
}
</script>

<style lang="scss" scoped>
    img{
        width: 100%;
    }

    h4{
        margin: 10px 0;
    }
</style>