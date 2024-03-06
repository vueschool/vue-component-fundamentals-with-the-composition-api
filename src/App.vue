<script setup>
import AppAlert from './components/AppAlert.vue'
import { ref } from 'vue'

const alerts = ref([
  {
    type: 'success',
    message: 'Your purchase has been confirmed!'
  },
  {
    type: 'error',
    message: 'Error! Task failed successfully.'
  }
])
</script>

<template>
  <div class="p-5">
    <AppAlert
      v-for="alert in alerts"
      :key="alert.message"
      :type="alert.type"
      @closed="alerts = alerts.filter((a) => a.message !== alert.message)"
    >
      {{ alert.message }}
    </AppAlert>

    <pre>
      {{ alerts }}
    </pre>
  </div>
</template>
