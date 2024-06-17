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
    methods: {
        getListCards(characterName = null) {
            if (characterName != null) {
                axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=39&offset=0&archetype=' + characterName)
                    .then((response) => {
                        // handle success
                        console.log(response.data.data);
                        this.ListCards = response.data.data;
                    })
                    .catch((error) => {
                        // handle error
                        console.log(error);
                    })
                    .finally(() => {
                        // always executed
                    });
            } else {
                axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=39&offset=0')
                    .then((response) => {
                        // handle success
                        console.log(response.data.data);
                        this.ListCards = response.data.data;
                    })
                    .catch((error) => {
                        // handle error
                        console.log(error);
                    })
                    .finally(() => {
                        // always executed
                    });
            }
        },
        searchCharacter(searchedString) {
            console.log(searchedString);
            this.getListCards(searchedString);
        }
    },
    created() {
        this.getListCards();
    }
}
</script>

<template>
<main>
    <MainSearch @searched="searchCharacter"/>
    <div class="container-cards">
        <MainListCards :cards="ListCards" />
    </div>
</main>
</template>

<style scoped>
main{
    background-color: orange;
    padding: 3rem;
}
.container-cards{
    background-color: white;
    width: 85%;
    margin: 0 auto;
}
</style>