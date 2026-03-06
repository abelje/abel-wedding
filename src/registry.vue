<script setup>
  import SectionHeader from "@/components/sectionHeader.vue";
  const items = [
    'Plates',
    'Cups',
    'Rubber Spatulas',
    'Queen Size Bedding',
    'Dish Towels',
    'Dish Cloths',
    'Vacuum',
    'Mop',
    'Stand Mixer',
    'Potholders',
    'Pizza Stone'
  ]
</script>

<template>
  <SectionHeader
      title="Registry"
      subtitle="Access our registry via the Knot or look at the overview on the side!"
  />
  <v-btn class="mt-4 ml-4 bg-green-darken-2" href="https://registry.theknot.com/kristen-danielewicz-jonathan-abel-june-2027-in/73629386">The Knot Registry</v-btn>
  <v-row>
    <v-col class="d-flex mt-2 justify-center">
      <iframe src="https://registry.theknot.com/kristen-danielewicz-jonathan-abel-june-2027-in/73629386" title="The Knot Registry" width="700" height="750"></iframe>
    </v-col>
    <v-col class="mr-4">
      <h1>Thank You!</h1>
      <p class="ma-5">We are thrilled to have you come celebrate with us! Thank you for supporting us as we head into a exciting new
        stage of our lives. If you would like to support us with a gift, a link to our registry is on the left.</p>
      <h1 class="mt-2">Overview</h1>
      <v-divider/>
      <v-list>
        <v-list-item
          v-for="item in items"
          :key="item"
          >{{ item }}</v-list-item>
      </v-list>
      <br>
    </v-col>
  </v-row>

</template>

<style scoped>

</style>