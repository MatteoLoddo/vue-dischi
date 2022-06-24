<template>
    <div class="bg-card text-center ">
        <div class="img-card p-3">
            <img :src="linkImg" :alt="`immagine del disco ${author}`">
        </div>
        <h6 class="text-light p-2">{{DiscTitle}}</h6>
        <span class="text-muted fs-7"><strong>{{author}}</strong></span>
    </div>
</template>

<script>
export default{

    props:{
        DiscTitle:String,
        author:String,
        linkImg:String,

    }

}
</script>

<style lang="scss" scoped>
.bg-card{
    background-color: #2E3A46 ;
    height: 100%;
    .fs-7{
        font-size: 0.8rem;

    }
}

.img-card{
    img{
        width: 100%;
        height: 100%;
    }
}
</style>