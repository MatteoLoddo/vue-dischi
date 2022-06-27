<template>
    <div class="container my-bg-main">
        <span class="text-light">Filtro attivo:{{genreSearch}}</span>
        <div class="row row-cols-5 g-3">
            <div class="col align-items-stretch" v-for="(disc, i) in filterAlbum" :key="i">
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
    components:{DiscElementVue,},

    props:{
        genreSearch:String,
    },
    data(){
        return{
        DiscList:[],
        apiURL: 'https://flynn.boolean.careers/exercises/api/array/music',
        
        };
        
    },
    computed:{
        filterAlbum(){
            if(!this.genreSearch){
                return this.DiscList
            }
            return this.DiscList.filter((element)=>{
                return element.genre === this.genreSearch;
            })
        }

    },
    methods:{
        // creo una funzione per fare la chiamata all API 
        fetchDiscList(){
            axios.get(this.apiURL)
            .then((object) =>{
                console.log(object.data.response);
                this.DiscList.push(...object.data.response)

                this.$emit("genreUpdate", this.genreList())
            })
            
        },
        genreList(){
                const  listGenre = []; 

                this.DiscList.forEach((element)=>{
                    if(!listGenre.includes(element.genre)){
                        listGenre.push(element.genre)
                    }
                })
                return listGenre
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