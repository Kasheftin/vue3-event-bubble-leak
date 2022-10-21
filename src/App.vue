<template>
  <div class="wrapper">
    <Test1 @change="changeHandler" />
  </div>
</template>

<script setup lang="ts">
import Test1 from './Test1.vue'
const changeHandler = (payload: any) => {
  if (payload?.someAdditionalData) {
    console.log('Correct @change event triggered by Test1', payload)
  } else {
    console.log('Leaked @change event somehow passed by event handler in Test1', payload)
  }
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
