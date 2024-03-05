<script setup>
import PlanPicker from './components/PlanPicker.vue'
import { ref } from 'vue'
const show = ref(true)
</script>

<template>
  <div class="content">
    <h1 class="title">Coffee Plans</h1>

    <h2 class="subtitle">
      We travel the world to source the very best single origin coffee for you
    </h2>

    <label for=""><input type="checkbox" v-model="show" />Show plan picker</label>

    <PlanPicker v-if="show" />
  </div>
</template>
