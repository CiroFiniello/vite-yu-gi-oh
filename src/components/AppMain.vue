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
                axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=39&offset=0')
                .then( (response) => {
                    // handle success
                    console.log(response.data.data);
                    this.ListCards = response.data.data
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
    <div class="container-cards">
            <MainListCards :cards="ListCards" />
        </div>
    </main>
</template>

<style scoped>
main{
    background-color: orange;
    padding: 3rem;
    .container-cards{
        background-color: white;
        width: 85%;
        margin: 0 auto;
    }
}
</style>