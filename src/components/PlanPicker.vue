<script setup>
import { ref } from 'vue'
import CoffeePlan from './CoffeePlan.vue'
const plans = ref(['The Single', 'The Curious', 'The Addict', 'The Hacker'])

const selectedCoffeePlan = ref()

function handleSelectCoffeePlan(name) {
  selectedCoffeePlan.value = name
}
</script>
<template>
  <div class="plans">
    {{ selectedCoffeePlan }}
    <CoffeePlan
      v-for="plan in plans"
      :key="plan"
      :name="plan"
      :selected="plan === selectedCoffeePlan"
      @selected="handleSelectCoffeePlan"
    ></CoffeePlan>
  </div>
</template>
