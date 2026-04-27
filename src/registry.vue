<script setup>
  import SectionHeader from "@/components/sectionHeader.vue";
  import {onMounted, ref} from "vue";

  const registries = ref([])
  const loading = ref(true)
  const error = ref('')

  async function loadRegistries() {
    loading.value = true
    error.value = ''

    try {
      const response = await fetch('/api/registry')

      if (!response.ok) {
        throw new Error('Failed to load registries.')
      }

      const data = await response.json()

      registries.value = data.map((reg) => ({
        id: reg.id,
        name: reg.name,
        link: reg.link,
      }))
    }
    catch(err) {
      error.value = err.message || 'Something went wrong while loading registries.'
    }
    finally {
      loading.value = false
    }
  }

  onMounted(() => {
    loadRegistries()
  })
</script>

<template>
  <SectionHeader
      title="Registry"
      subtitle="Access our registry via the Knot or Amazon!"
  />

  <v-btn class="mt-4 ml-4 mb-6 bg-green-darken-2" v-for="registry in registries" :key="registry" :href="registry.link">{{ registry.name }}</v-btn>
  <v-divider></v-divider>
  <v-row>
    <v-col class="ml-4 mr-4">
      <h1>Thank You!</h1>
      <p class="ma-5">We are thrilled to have you come celebrate with us! Thank you for supporting us as we head into a exciting new
        stage of our lives. If you would like to support us with a gift, a link to our registry is above.</p>
      <br>
    </v-col>
    <v-col class="d-flex mt-2 justify-center">
      <iframe src="https://registry.theknot.com/kristen-danielewicz-jonathan-abel-june-2027-in/73629386" title="The Knot Registry" width="700" height="750"></iframe>
    </v-col>
  </v-row>

</template>

<style scoped>

</style>