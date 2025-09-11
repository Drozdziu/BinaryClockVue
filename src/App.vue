<script setup>
import binaryNumber from './components/binaryNumber.vue'
// const time = new Date()
let hours = 8//time.getHours()
let minutes = 12//time.getMinutes()
let seconds = 24//time.getSeconds()
</script>

<template>
  <div class="container">
    <binary-number :msg="2" :time="hours" :limit="2"/>
    <binary-number :msg="4" :time="hours" :limit="9"/>
    <binary-number :msg="3" :time="minutes" :limit="5"/>
    <binary-number :msg="4" :time="minutes" :limit="9"/>
    <binary-number :msg="3" :time="seconds" :limit="5"/>
    <binary-number :msg="4" :time="seconds" :limit="9"/>
  </div>
</template>

<style scoped>
.container {
  margin-top: 10%;
  display: flex ;
  justify-content: center; /* ustawia na środku w poziomie */
}
</style>
