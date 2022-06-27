<template>
    <div class="d-flex justify-content-between">
        <img src="../../public/img/spotify-2.svg">
        <FilterDisc :list-genre="listGenre"
                    @searchGenre="$emit('searchGenre', $event)"
        ></FilterDisc>
    </div>
</template>



<script>

import FilterDisc from '../components/FilterDisc.vue';


export default{
    
    components:{FilterDisc,},

    props:{
        listGenre:Array,
    }

}


</script>

<style lang="scss" scoped>
div{
    background-color:#2E3A46;
    padding:0.5rem;
    img{
        width:50px;
    }
}
</style>