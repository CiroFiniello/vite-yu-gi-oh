<script>
import MainCard from './MainCard.vue';
export default {
    components:{
        MainCard
    },
    data() {
        return 
            {
        }
    },
    props:{
        cards:{
            type: Array,
            required: true
        }
    }
}
</script>

<template>
    <article v-for="cards in cards" :key="cards.id">
        <div class="card w-100">
        <img :src="cards.card_images[0].image_url" class="card-img-top" alt="...">
        <div class="card-body">
        <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p>
        </div>
    </div>
    </article>
    <p>
        Numbers of cards : {{ cards.length }}
    </p>
    <MainCard/>
</template>

<style scoped>

</style>