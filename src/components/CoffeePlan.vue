<script setup>
import { ref } from 'vue'
const props = defineProps({
  name: { type: String, default: 'Default Plan' },
  selected: { type: Boolean, default: false }
})

const emit = defineEmits(['selected'])

function selectPlan() {
  emit('selected', props.name)
}
</script>
<template>
  <div @click="selectPlan" class="plan" :class="{ 'active-plan': selected }">
    <div class="description">
      <span class="title">{{ name }} </span>
    </div>
  </div>
</template>
