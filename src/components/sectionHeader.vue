<script setup>
defineProps({
  title: { type: String, required: true },
  subtitle: { type: String, default: '' }
})
</script>

<template>
  <div class="d-flex align-start flex-wrap text-center justify-center bg-green-darken-2">
    <div>
      <h1 class="text-h2 mb-1 mt-1">{{ title }}</h1>
      <br>
      <div v-if="subtitle" class="text-center text-lg-body-1 text-white mb-2">{{ subtitle }}</div>
    </div>

    <div class="d-flex align-center flex-wrap ga-2">
      <slot name="right"></slot>
    </div>
  </div>
  <v-divider color="pink" thickness="12" ></v-divider>
</template>