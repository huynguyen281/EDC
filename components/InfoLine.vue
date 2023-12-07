<template>
  <div class="flex gap-2">
    <div class="font-semibold flex items-center justify-start gap-3">
      <slot></slot>
      <span>{{ label }}:</span>
    </div> 
    <span class="flex items-center gap-2 opacity-60">
      {{ text }}
    </span>
  </div>
</template>
<script setup lang="ts">
defineProps({
  label: {
    type: String,
    default: '',
  },
  text: {
    type: String,
    default: '',
  },
})
</script>