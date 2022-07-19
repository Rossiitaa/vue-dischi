<template>
        <div class="container">
            <DiskCard v-for="(disk, index) in disks" :key="index" 
            :poster="disk.poster" 
            :title="disk.title" 
            :author="disk.author" 
            :year="disk.year"
            />
        </div>
</template>

<script>
import axios from 'axios';
import DiskCard from './DiskCard.vue';

export default {
    components: {
        DiskCard,
    },

    data() {
        return {
            disks: [],
        };
    },

    methods: {
        getDisks: function() {
            axios.get("https://flynn.boolean.careers/exercises/api/array/music")
            .then((response) => {
                this.disks = response.data.response;
            })
        }
    },
    created() {
        this.getDisks();
        }
    }

</script>

<style lang="scss">
@import '~bootstrap/scss/bootstrap.scss';
@import '../styles/general.scss';

div.container {
    width: 60%;
    margin: 0 auto;
    display: flex;
    flex-wrap: wrap;
    gap: 2rem;
}
</style>