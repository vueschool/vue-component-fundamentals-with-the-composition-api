<script setup>
import { computed, ref } from 'vue'
import IconError from './icons/IconError.vue'
import IconWarning from './icons/IconWarning.vue'
import IconSuccess from './icons/IconSuccess.vue'
import IconInfo from './icons/IconInfo.vue'
const props = defineProps({
  type: { type: String, default: 'info' }
})

const emit = defineEmits(['closed'])

const alertType = computed(() => {
  return {
    info: 'alert-info',
    warning: 'alert-warning',
    error: 'alert-error',
    success: 'alert-success'
  }[props.type]
})
const icon = computed(() => {
  return {
    info: IconInfo,
    warning: IconWarning,
    success: IconSuccess,
    error: IconError
  }[props.type]
})

const closed = ref(false)
function close() {
  closed.value = true
  emit('closed')
}
</script>
<template>
  <div v-if="!closed" role="alert" :class="`alert ${alertType}`">
    <component :is="icon"></component>
    <span><slot></slot></span>
    <button @click="close">ⅹ</button>
  </div>
</template>
