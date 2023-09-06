<template>
  <section>
    <div class="box">
      <div class="batteryShape">
        <div class="level">
          <div class="percentage" :style="{ width: batteryLevel }" />
        </div>
      </div>
      <div class="percent">{{ batteryLevel }}</div>
      <input v-model="userBatteryLevel" placeholder="輸入電池電量" @input="updateBatteryLevel">
    </div>
  </section>
</template>
<script setup>
import { ref, onMounted } from 'vue'

const userBatteryLevel = ref(50)
const batteryLevel = ref('50%')

const updateBatteryLevel = () => {
  if (!isNaN(userBatteryLevel.value)) {
    userBatteryLevel.value = Math.min(100, Math.max(0, userBatteryLevel.value))
    batteryLevel.value = userBatteryLevel.value + '%'
  }
}

onMounted(() => {
  // navigator.getBattery().then((battery) => {
  //   userBatteryLevel.value = battery.level * 100
  //   updateBatteryLevel()

  // battery.addEventListener('levelchange', () => {
  //   userBatteryLevel.value = battery.level * 100
  //   updateBatteryLevel()
  // })
  // })
})
</script>

