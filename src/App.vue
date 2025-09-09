<script setup>
import binaryNumber from './components/binaryNumber.vue'
</script>

<template>
  <div class="container">
    <binary-number msg="2"/>
    <binary-number msg="4"/>
    <binary-number msg="3"/>
    <binary-number msg="4"/>
    <binary-number msg="3"/>
    <binary-number msg="4"/>
  </div>
</template>

<style scoped>
.container {
  margin-top: 10%;
  display: flex ;
  justify-content: center; /* ustawia na środku w poziomie */
}
</style>
