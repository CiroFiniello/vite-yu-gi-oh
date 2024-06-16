<script>
import MainSearch from './MainSearch.vue';
import MainListCards from './MainListCards.vue';
export default {
    components:{
        MainSearch,
        MainListCards
    },
    data() {
        return 
            {
        }
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