<script>
    export default {
    name: 'binary-number',
    props: {
        msg: Number,
        time: Number,
    },
    methods: {
        lightup(){
            const boxes =  Array.from(this.$el.getElementsByClassName('number')).reverse() // this.$el - tylko w tym komponencie
            if(this.time % 2 == 1 && this.time != 0) boxes[0].style.backgroundColor = "rgb(253, 218, 58)"
            else boxes[0].style.backgroundColor = "black"

            if(this.time % 4 == 2 || this.time % 4 == 3) boxes[1].style.backgroundColor = "rgb(253, 218, 58)"
            else boxes[1].style.backgroundColor = "black"
            if(this.msg >= 3){
                if(this.time >= 4 && this.time <= 7) boxes[2].style.backgroundColor = "rgb(253, 218, 58)"
                else boxes[2].style.backgroundColor = "black"
            }
            if(this.msg == 4){
                if(this.time >= 8) boxes[3].style.backgroundColor = "rgb(253, 218, 58)"
                else boxes[3].style.backgroundColor = "black"
            } 
        }
        
    },
    mounted() {
        this.lightup()
    },
    updated() {
        this.lightup()
    }
}
</script>
<template>
<div id="container" class="col-1 mx-2 my-2"> 
    <div class="number " v-if="msg >= 4"></div>
    <div class="empty " v-else></div>
    <div class="number " v-if="msg >= 3"></div>
    <div class="empty " v-else></div>
    <div class="number "></div>
    <div class="number "></div>
</div>
</template>

<style scoped>
    .number, .empty{
        aspect-ratio: 1 / 1;
        width: 100%;
        margin: 1vh;
        transition: 200ms;
        border-radius: 30%;
    }
    .number{
        background-color: rgb(253, 218, 58);
        transition: 200ms;
    }
    p{
        color: #fff;
    }
</style>