<template>
    <div class="d-flex">
        <div class="image-container m-auto">
            <img class="img-fluid" src="https://acegif.com/wp-content/uploads/loading-2.gif" alt="loader">
        </div>
    </div>
</template>

<script>
export default {
    name: 'Loader',
}
</script>

<style lang='scss'>
    div.image-container {
        width: 100%;
        height: 100%;
        display: flex;
        justify-content: center;
        align-items: center;
        position: absolute;
        top: 0;
    }
</style>