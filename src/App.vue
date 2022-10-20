<template>
  <div class="wrapper">
    <Test1 @change="changeHandler" />
  </div>
</template>

<script setup lang="ts">
import Test1 from './Test1.vue'
const changeHandler = () => {
  console.log('Change event triggered in App.vue')
}
</script>

<style>
.wrapper {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}
</style>
