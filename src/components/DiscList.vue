<template>
    <div class="container my-bg-main">
        <div class="row row-cols-5 g-3">
            <div class="col align-items-stretch" v-for="(disc, i) in DiscList" :key="i">
            <DiscElementVue
            :linkImg="disc.poster"
            :author="disc.author"
            :DiscTitle="disc.title"
            >
            </DiscElementVue>
            </div>
        </div>
    </div>
</template>

<script>
import DiscElementVue from "./DiscElement.vue";
import axios from "axios"
export default{
    components:{DiscElementVue},
    data(){
        return{
        DiscList:[],
        apiURL: 'https://flynn.boolean.careers/exercises/api/array/music',

        };
    },
    methods:{
        // creo una funzione per fare la chiamata all API 
        fetchDiscList(){
            axios.get(this.apiURL)
            .then((object) =>{
                console.log(object.data.response);
                this.DiscList.push(...object.data.response)
            })

        }
    },
    // con mounted permetto alla funzione richiamata di eseguirsi all avvio della pagina
    mounted(){
        this.fetchDiscList()
    }
}
</script>

<style lang="scss" scoped>


</style>