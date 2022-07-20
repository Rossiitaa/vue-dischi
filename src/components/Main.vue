<template>
    <main>
        <DiskContainer />
    </main>
</template>

<script>
import DiskContainer from './DiskContainer.vue';

export default {

    components: {
        DiskContainer,
    },

}
</script>

<style lang="scss" scoped>
    main {
        height: 100vh;
        background-color: #1f2d3b;
        padding-top: 4.5rem;
    }
</style>