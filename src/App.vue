<script setup>
import binaryNumber from './components/binaryNumber.vue'
// const time = new Date()
let hours = 8//time.getHours()
let minutes = 12//time.getMinutes()
let seconds = 24//time.getSeconds()
</script>

<template>
  <div class="container">
    <binary-number :msg="2" :time="hours"/>
    <binary-number :msg="4" :time="hours"/>
    <binary-number :msg="3" :time="minutes"/>
    <binary-number :msg="4" :time="minutes"/>
    <binary-number :msg="3" :time="seconds"/>
    <binary-number :msg="4" :time="seconds"/>
  </div>
</template>

<style scoped>
.container {
  margin-top: 10%;
  display: flex ;
  justify-content: center; /* ustawia na środku w poziomie */
}
</style>
