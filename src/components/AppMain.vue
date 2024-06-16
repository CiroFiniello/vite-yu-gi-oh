<script>
import MainSearch from './MainSearch.vue';
import MainListCards from './MainListCards.vue';
import axios from 'axios';

export default {
    components: {
        MainSearch,
        MainListCards
    },
    data() {
        return {
            ListCards: [],
        };
    },
        methods:{
            getListCards(){
                axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0')
                .then(function (response) {
                    // handle success
                    console.log(response);
                })
                .catch(function (error) {
                    // handle error
                    console.log(error);
                })
                .finally(function () {
                    // always executed
                });
            }
        },
        created(){
            this.getListCards();
        }
    }

</script>

<template>
<main>
    <h1>Main</h1>
    <MainSearch/>
    <MainListCards/>
</main>
</template>

<style scoped>

</style>