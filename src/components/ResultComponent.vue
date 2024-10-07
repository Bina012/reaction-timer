<template>
    <p v-if="showResult">Reaction time : {{ score }} ms</p>

</template>

<script>

export default {
    data (){
        return{
            rank: null
        }
    },
    methods :{

    },
    props : ['score','showResult'],


}
</script>

<style scoped>
.rank{
    font-size:1.4rem;
    color: #0faf87;
    font-weight:
}
</style>
