<script setup>
defineProps({
  name: { type: String, default: 'Default Plan' }
})
</script>
<template>
  <div class="plan">
    <div class="description">
      <span class="title">{{ name }} </span>
    </div>
  </div>
</template>
