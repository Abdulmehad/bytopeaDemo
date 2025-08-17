<template>
  <a :href="link" class="block w-full h-full flex flex-col items-center justify-center text-center p-4"
     :class="ctaClasses">
  <h2 class="text-2xl md:text-3xl  mb-4">{{ title }}</h2>
  <button class="bg-white/10 text-black px-6 py-3 rounded text-lg border md:text-xl">
      {{ button }}
    </button>
  </a>
</template>

<script setup>
import { computed } from "vue"


const props = defineProps({
  title: { type: String, required: true },
  button: { type: String, required: true },
  link: { type: String, required: true },
  mode: { type: String, default: "square" },
  color: { type: String, default: "bg-white" }
})

const ctaClasses = computed(() => {
  if (props.mode === "rectangle") {
    const bg = props.color || "bg-white/70"
    return `${bg} md:bg-white/70 absolute top-1/2 right-0 transform -translate-y-1/2 max-w-xs rounded shadow`
  }
  return `${props.color} rounded`
})
</script>