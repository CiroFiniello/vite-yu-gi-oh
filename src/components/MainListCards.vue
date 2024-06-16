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
    <div class="row p-3">
        <article v-for="cards in cards" :key="cards.id" class="col-2">
            <div class="card w-100">
            <img :src="cards.card_images[0].image_url" class="card-img-top" alt="...">
            <div class="card-body">
            <p class="card-text">{{ cards.name }}</p>
            <p>{{ cards.archetype }}</p>
            </div>
        </div>
    </article>
    </div>
    <p>
        Numbers of cards : {{ cards.length }}
    </p>
    <!-- <MainCard/> -->
</template>

<style scoped>
article{
    width: 200px;
    margin: 0 auto;
}
.card-body{
    background-color: orange;
    margin-bottom: 2rem;
    height: 150px;
    .card-text{
        color: white;
        font-weight: bold;
    }
}
</style>