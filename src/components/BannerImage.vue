<template>
  <a :href="link" class="block w-full h-full">
    <img
      :src="src"
      :alt="alt"
      class="w-full h-full object-cover"
    />
  </a>
</template>

<script setup>
defineProps({
  src: { type: String, required: true },
  alt: { type: String, default: '' },
  link: { type: String, required: true },
})
</script>