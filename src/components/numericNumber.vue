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
    <p class="fs-1 col-12">{{ hour < 10 ? '0' + hour : hour }} : {{ minutes < 10 ? '0' + minutes : minutes }} : {{ seconds < 10 ? '0' + seconds : seconds }}</p>
</template>

<style scoped>
p {
    /* font-size: 50px; */
    /* letter-spacing: 30px; */
    color: rgb(253, 218, 58);
    text-align: center;
}
</style>