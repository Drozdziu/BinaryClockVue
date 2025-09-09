<script>
    export default {
    name: 'binaryNumber ',
    props: {
        msg: String
    },
    data() { // zmienne
        const time = new Date()
        return {
            hours: time.getHours(),
            minutes: time.getMinutes(),
            seconds: time.getSeconds(),
        }
    },
    methods: { }// metody
}
</script>
<template>
<div id="container"> 
    <div class="number"></div>
    <div class="number"></div>
    <div class="number" v-if="msg === '3' || msg === '4'"></div>
    <div class="number"v-if="msg === '4'"></div> 
</div>
</template>

<style scoped>
    .number{
        background-color: black;
        height: 100px;
        width: 100px;
        margin: 10px;
    }
</style>