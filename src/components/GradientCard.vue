<script setup lang="ts">
const { style_str, index } = defineProps<{ style_str: string; index: number }>()
const value = ref(20)
const inner_style = computed(() => {
  let new_style = style_str
  if (style_str.includes('--s'))
    new_style = new_style.replace(/--s:\s*\d+px/, `--s: ${value.value}px`)

  else if (style_str.includes('--r'))
    new_style = new_style.replace(/--r:\s*\d+px/, `--r: ${value.value}px`)

  return new_style
})
const style_str_c = computed(() => {
  return `
    <style scoped>
      .GradientCard${index} {
        width: 400px;
        margin: auto;
        height: 400px;
        ${inner_style.value}
      }
    </style>
  `
})
</script>

<template>
  <div v-html="style_str_c" />
  <div :class="`GradientCard${index}`" />
  <div>
    <input v-model="value" type="range" min="10" max="100">
  </div>
</template>
