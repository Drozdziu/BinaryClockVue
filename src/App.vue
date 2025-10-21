<script>
import binaryNumber from './components/binaryNumber.vue';
import numericNumber from './components/numericNumber.vue';
export default {
  components: {
    binaryNumber,
    numericNumber
  },
  data() {
    return {
      hours: 0, hour1: 0, hour2: 0,
      minutes: 0, minutes1: 0, minutes2: 0,
      seconds: 0, seconds1: 0, seconds2: 0
    }
  },
  methods: {
    updateTime() {
      const now = new Date();
      this.hours = now.getHours();
      this.minutes = now.getMinutes();
      this.seconds = now.getSeconds();
      this.hour1 = Math.floor(this.hours / 10); this.hour2 = Math.floor(this.hours % 10); 
      this.minutes1 = Math.floor(this.minutes / 10); this.minutes2 = Math.floor(this.minutes % 10); 
      this.seconds1 = Math.floor(this.seconds / 10); this.seconds2 = Math.floor(this.seconds % 10); 
    }
  },
  mounted(){
    this.updateTime();
    setInterval(this.updateTime, 1000);
  }
} 
// import { computed, ref } from 'vue'
// const hours = ref(0)
// const minutes = ref(0)
// const seconds = ref(0)
// let hour1 = computed(() => Math.floor(hours.value / 10)), hour2 = computed(() => hours.value % 10)
// let minutes1 = computed(() => Math.floor(minutes.value / 10)), minutes2 = computed(() => minutes.value % 10)
// let seconds1 = computed(() => Math.floor(seconds.value / 10)), seconds2 = computed(() => seconds.value % 10)
// function updateTime() {
//   const now = new Date()
//   hours.value = now.getHours()
//   minutes.value = now.getMinutes()
//   seconds.value = now.getSeconds()
// }
// setInterval(updateTime, 1000)
// updateTime()
</script>

<template>
  <div class="container">
    <binary-number :msg="2" :time="hour1" />
    <binary-number :msg="4" :time="hour2" />
    <binary-number :msg="3" :time="minutes1" />
    <binary-number :msg="4" :time="minutes2" />
    <binary-number :msg="3" :time="seconds1" />
    <binary-number :msg="4" :time="seconds2" />
  </div>
  <numeric-number :hour="hours" :minutes="minutes" :seconds="seconds"></numeric-number>
</template>

<style scoped>
.container {
  margin-top: 10%;
  display: flex;
  justify-content: center;
}
</style>
