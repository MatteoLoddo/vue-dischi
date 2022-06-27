<template>
    <div class="mt-3 d-flex align-items-baseline">
        <div class="input-group">
            <select type="text" class="form-select" v-model="genre">
                <option value="">None</option>
                <option v-for="(genere,i) in listGenre" :key="i" :value="genere">{{genere}}</option>
            </select>
            <button class="btn btn-secondary" @click="onClickSearch">Cerca</button>
        </div>
    </div>
</template>

<script>

export default{
    props:{
        listGenre:Array,


    },
    data(){
        return{
            genre:"",
        }
    },

    

    methods:{
        onClickSearch(){
            this.$emit("searchGenre", this.genre)
            console.log(this.genre);
        }

    }
}
</script>

<style>
</style>
