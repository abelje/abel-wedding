<script setup>
  import SectionHeader from "@/components/sectionHeader.vue";
  import LocationCard from "@/components/locationCard.vue";

  const locations = [
    {
      id: 1,
      title: 'Ceremony',
      name: 'Zion Evangelical Lutheran Church',
      address: '1610 Main Street, Crete, IL 60417',
      time: '12:00',
      image: '<iframe src="https://www.google.com/maps/embed?pb=!4v1772766381997!6m8!1m7!1sSs1jjHzM9DmPQ1Mfzw4Wnw!2m2!1d41.43586154411035!2d-87.63097924515138!3f322.39150595166524!4f14.793582422710472!5f0.7820865974627469" width="600" height="450" style="border:0;" allowfullscreen="" loading="lazy" referrerpolicy="no-referrer-when-downgrade"></iframe>',
      description: 'Dress: Sunday best'
    },
    {
      id: 2,
      title: 'Reception',
      name: 'Villa Cesare Banquets & Events',
      address: '900 Eagle Ridge Dr, Schererville, IN 46375',
      time: '6:00PM - 12:00AM',
      image: '<iframe src="https://www.google.com/maps/embed?pb=!4v1772766212595!6m8!1m7!1sgoylmUPa6dqHTZB-JXQ6jg!2m2!1d41.50534737064918!2d-87.47435834659535!3f252.05691048207015!4f-6.318704914042613!5f0.7820865974627469" width="600" height="450" style="border:0;" allowfullscreen="" loading="lazy" referrerpolicy="no-referrer-when-downgrade"></iframe>',
      description: 'Dress: Sunday best'
    },
  ]
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