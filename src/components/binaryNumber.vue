<script>
    export default {
    name: 'binary-number',
    props: {
        msg: Number,
        time: Number,
        limit: Number,
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
            console.log(this.time)
            this.lightup()
        },
        lightup(){
            const boxes = this.$el.getElementsByClassName('number') // this.$el - tylko w tym komponencie
            console.log(boxes)
            if(this.time % 2 == 1 && this.time != 0) boxes[0].style.backgroundColor = "white"
            else boxes[0].style.backgroundColor = "black"

            if(this.time % 4 == 2 || this.time % 4 == 3) boxes[1].style.backgroundColor = "white"
            else boxes[1].style.backgroundColor = "black"
            if(this.msg == 3){
                if(this.time >= 4 && this.time <= 7) boxes[2].style.backgroundColor = "white"
                else boxes[2].style.backgroundColor = "black"
            }
            if(this.msg == 4){
                if(this.time >= 8)boxes[3].style.backgroundColor = "white"
                else boxes[3].style.backgroundColor = "black"
            } 
        }
     },
    mounted() {
        this.test()
        this.lightup()
    },
    updated() {
        this.lightup()
    }
}
</script>
<template>
<div id="container"> 
    <div class="number" v-if="msg >= 3"></div>
    <div class="empty" v-else></div>
    <div class="number"v-if="msg >= 4"></div>
    <div class="empty" v-else></div>
    <div class="number"></div>
    <div class="number"></div>

    <p> {{ this.time }}</p>
</div>
</template>

<style scoped>
    .number, .empty{
        background-color: black;
        height: 100px;
        width: 100px;
        margin: 10px;
        transition: 200ms;
        border-radius: 10px;
    }
    .number{
        background-color: black;
        transition: 200ms;
    }
    p{
        color: #fff;
    }
</style>