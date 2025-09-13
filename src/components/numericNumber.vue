<script>
    export default {
    name: 'numeric-number',
    props: {
        hour: Number,
        minutes: Number,
        seconds: Number
    },
}
</script>
<template>
    <p> {{ hour < 10 ? '0'+hour: hour }} : {{ minutes < 10 ? '0'+minutes : minutes }} : {{ seconds < 10 ? '0' + seconds : seconds }}</p>
</template>

<style scoped>
    p{
        font-size: 50px;
        color: aliceblue;
        text-align: center;
    }
</style>