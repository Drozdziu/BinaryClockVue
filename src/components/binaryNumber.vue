<script>
    export default {
    name: 'binary-number',
    props: {
        msg: Number,
        time: Number,
        //testNumber: 0  tak nie robimy
        testNumber: {
            type: Number,
            default: 0
        }  
    },
    data(){
        return{
            testTime: this.testNumber,
        }
    },
    methods: {
        test(){
            console.log(this.testTime)
            this.testTime+=1
            this.lightup()
        },
        lightup(){
            const boxes = this.$el.getElementsByClassName('number') // this.$el - tylko w tym komponencie
            console.log(boxes)
            if(this.testTime % 2 == 1 && boxes[0]) boxes[0].style.backgroundColor = "white"
            else boxes[0].style.backgroundColor = "black"
            // if(this.testTime >= 8 && boxes[3]) boxes[3].style.backgroundColor = "white"
        }
     },
    mounted() {
        this.test()
        this.lightup()
    }
}
</script>
<template>
<div id="container"> 
    <button @click="test">test</button>
    <div class="number"></div>
    <div class="number"></div>
    <div class="number" v-if="msg >= 3"></div>
    <div class="number"v-if="msg >= 4"></div>
    
</div>
</template>

<style scoped>
    .number{
        background-color: black;
        height: 100px;
        width: 100px;
        margin: 10px;
        transition: 200ms;
        border-radius: 10px;
    }
</style>