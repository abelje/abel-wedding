<script setup>
  import SectionHeader from "@/components/sectionHeader.vue";
  import LocationCard from "@/components/locationCard.vue";
  import {onMounted, ref} from "vue";
  const locations = ref([])
  const loading = ref(true)
  const error = ref('')

  async function loadLocations() {
    loading.value = true
    error.value = ''

    try {
      const response = await fetch('/api/locations')

      if (!response.ok) {
        throw new Error('Failed to load locations.')
      }

      const data = await response.json()

      locations.value = data.map((loc) => ({
        id: loc.id,
        title: loc.title,
        name: loc.name,
        address: loc.address,
        time: loc.time,
        image: loc.image,
        description: loc.description,
      }))
    }
    catch(err) {
      error.value = err.message || 'Something went wrong while loading locations'
    }
    finally {
      loading.value = false
    }
  }

  onMounted(() => {
    loadLocations()
  })
</script>

<template>
  <SectionHeader
      title="Locations"
      subtitle="Here is all the places of interest for our wedding!"
  />

  <v-row class="md-2 d-flex justify-center mt-4">
    <v-col
        v-for="loc in locations"
        :key="loc.id"
        cols="12"
        sm="6"
        md="4"
    >
      <LocationCard
          :title="loc.title"
          :time="loc.time"
          :address="loc.address"
          :name="loc.name"
          :image="loc.image"
          :description="loc.description"
      ></LocationCard>
    </v-col>
  </v-row>

</template>

<style scoped>

</style>