<script setup>
import { ref } from "vue";

const props = defineProps({
  title: {type:String, required:true},
  name: {type: String, required: true},
  address: {type: String, required: true},
  time: {type: String, required: true},
  image: {type: String, default: ''},
  description: {type: String, required: true},
});

const cardText = ref('')

async function copyAddress(address) {
  try {
    await navigator.clipboard.writeText(address)
    cardText.value = 'Address copied!'
  }
  catch (e) {
    cardText.value = 'Could not auto-copy. Please copy manually'
  }
  setTimeout(() => {
    cardText.value = ''
  }, 2000)
}

</script>

<template>
  <v-card class="h-100">
    <div v-html="image" class="d-flex justify-center">

    </div>
    <v-card-title class="text-h5">{{ title }}</v-card-title>
    <v-card-title class="text-sm-h6">{{ name }}</v-card-title>
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
    <v-card-actions>
      <v-btn variant="tonal" @click="copyAddress(address)">
        <v-icon start>mdi-content-copy</v-icon>
        Copy Address
      </v-btn>
      <v-spacer></v-spacer>
      <p>{{ cardText }}</p>
    </v-card-actions>
  </v-card>
</template>