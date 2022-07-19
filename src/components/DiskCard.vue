<template>
    <div class="cont-disk">
        <div>
            <img :src="poster" alt="title">
        </div>

        <h2> {{ title }} </h2>
        <p class="m-0"> {{ author }} </p>
        <span> {{ year }} </span>
    </div>
</template>

<script>
export default {

    props: {
        poster: String,
        title: String,
        author: String,
        year: String,
    }
}
</script>

<style lang="scss" scoped>
@import '~bootstrap/scss/bootstrap.scss';
@import '../styles/general.scss';

    .cont-disk {
        background-color: #2E3A46;
        width: calc((100% / 5) - 2rem);
        text-align: center;
        padding-bottom: 1rem;

        img {
            width: 100%;
            padding: 1rem;
        }

        h2 {
            color: #fff;
            font-size: 1.5rem;
            padding: 1rem;
            text-transform: uppercase;
        }

        span, p {
            color: #7b7e7f;
            font-size: 1rem;
        }
    }
</style>