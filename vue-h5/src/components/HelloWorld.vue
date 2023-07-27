<script setup lang="ts">
import { ref } from 'vue'

defineProps<{ msg: string }>()

const count = ref(0)

let environment = ref<any>('PC')
if (/Mobi|Android|iPhone/i.test(navigator.userAgent)) {
  // 当前设备是移动设备
  environment.value = '移动端设备'
} else {
  environment.value = 'PC'
}


</script>

<template>
  <h1>{{ msg }}</h1>
  <div class="box">
    <h1>{{ environment }}</h1>
  </div>



</template>

<style scoped>
h1 {
  width: 100px;
  height: 100px;
  border: 1px solid #000;
  font-size: 20px;
  margin: auto;
}

.box {
  width: 200px;
  height: 200px;
  background-color: red;
  margin: auto;
}
</style>
