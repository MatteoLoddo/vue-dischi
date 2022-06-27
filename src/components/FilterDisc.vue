<template>
    <div class="mt-3 d-flex align-items-baseline">
        <select class="form-select mb-3" aria-label=".form-select-lg example">
            <option value="" v-for="(genre,i) in listGenre" :key="i">{{genre}}</option>
        </select>
        <button class="btn btn-secondary">Cerca</button>
    </div>
</template>

<script>

export default{
    data(){
        return{

        }
    },

    props:{
        listGenre:Array,


    },

    methods:{

    }
}
</script>

<style>
</style>
