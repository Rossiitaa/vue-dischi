<template>
    <section>
        <div>
            <MusicalGenre @search="filter" />
        </div>

        <div v-if="isLoading">
            <Loader />
        </div>

        <div v-else class="container position-relative">
            <DiskCard v-for="(disk, index) in filterGenres" :key="index" 
            :poster="disk.poster" 
            :title="disk.title" 
            :author="disk.author" 
            :year="disk.year"
            :genre="disk.genre"
            />
        </div>


    </section>
</template>

<script>
import axios from 'axios';
import DiskCard from './DiskCard.vue';
import Loader from './Loader.vue';
import MusicalGenre from './MusicalGenre.vue';

export default {
    components: {
        DiskCard,
        Loader,
        MusicalGenre,
        
    },

    data() {
        return {
            disks: [],
            filterGenres: [],
            isLoading: true,

        };
    },

    methods: {
        getDisks: function() {
            axios.get("https://flynn.boolean.careers/exercises/api/array/music")
            .then((response) => {
                this.disks = response.data.response;
                this.filterGenres = this.disks;
            })
        setTimeout(() => {
            this.isLoading = false;
            }, 2000);
        },
        filter(selectedGenre) {
            
            if (selectedGenre === 'allGenres') {
                this.filterGenres = this.disks;
            } else {
                this.filterGenres = [...this.disks].filter( (disk) => 
                    disk.genre.toLowerCase().includes(selectedGenre));
            }
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