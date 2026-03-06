<script setup>
const props = defineProps({
  name: {type: String, required: true},
  address: {type: String, required: true},
  time: {type: String, required: true},
  image: {type: String, default: ''},
  description: {type: String, required: true},
});


</script>

<template>
  <v-card class="h-100">
    <div v-html="image" class="d-flex justify-center">

    </div>
    <v-card-title class="text-h6">{{ name }}</v-card-title>
    <v-card-subtitle>
      <v-icon size="small" class="mr-1">mdi-alarm</v-icon>
      {{ time }}
    </v-card-subtitle>

    <v-card-text>
      <div class="text-body-2 mb-3">
        <v-icon size="small" class="mr-1">mdi-map-marker</v-icon>
        {{ address }}
      </div>
      <div class="text-body-2">{{ description }}</div>
    </v-card-text>
  </v-card>
</template>