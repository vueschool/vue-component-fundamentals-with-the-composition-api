<script setup>
import { ref, onUnmounted, onMounted } from 'vue'
import CoffeePlan from './CoffeePlan.vue'
const plans = ref(['The Single', 'The Curious', 'The Addict', 'The Hacker'])

const selectedCoffeePlan = ref()

function handleSelectCoffeePlan(name) {
  selectedCoffeePlan.value = name
}

const count = ref(0)
const interval = setInterval(() => {
  count.value++
  console.log('hello')
}, 1000)

onUnmounted(() => {
  clearInterval(interval)
  console.log('Bye bye plan picker')
})
</script>
<template>
  <div class="plans">
    {{ count }}
    <CoffeePlan
      v-for="plan in plans"
      :key="plan"
      :name="plan"
      :selected="plan === selectedCoffeePlan"
      @selected="handleSelectCoffeePlan"
    ></CoffeePlan>
  </div>
</template>
