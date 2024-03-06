<script setup>
import FancyButton from './components/FancyButton.vue'
</script>

<template>
  <div class="content">
    <FancyButton>
      <template #icon="{ hover }">
        {{ hover ? '👋' : '💪' }}
      </template>
      Submit
    </FancyButton>
  </div>
</template>
