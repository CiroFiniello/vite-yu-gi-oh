<script>
export default {
    data() {
        return {
            searchedText: '',
        }
    }
}
</script>

<template>
<div class="container">
    <div class="row ">
        <div class="col-10 d-flex w-100 ">
            <div class="form-floating mb-3 w-100">
            <input type="text" class="form-control" id="search-input" placeholder="Cerca un archetipo"
            v-model="searchedText">
            <label for="search-input">Archetipo</label>
        </div>
        <div class="col-2">
            <button class="btn btn-primary btn-xl fs-3 w-100" @click="$emit('searched', searchedText)">Search</button>
        </div>
</div>
    </div>
</div>
</template>

<style scoped>

</style>