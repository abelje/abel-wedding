<script setup>
import SectionHeader from "@/components/sectionHeader.vue";
</script>

<template>
  <SectionHeader
      title="Photos"
      subtitle="Help us to capture moments of our special day by uploading your photos to our album!"
  />

  <v-btn class="ma-4 bg-green-darken-2" href="https://photos.app.goo.gl/6u4BqKFx65DPGPt27">Google Photos</v-btn>
  <v-btn class="ma-4 bg-green-darken-2" href="https://albums.ente.io/?t=5VJCIENTQW#GEDqz9zWC1kDRiJNPKvP2UxS6jtFjWMpucitrbn2ZC88">Ente</v-btn>
  <v-divider></v-divider>
<!--  Use ente for embed code-->
  <div class="d-flex justify-center mt-10 mr-3 ml-3">
    <iframe src="https://embed.ente.io/?t=5VJCIENTQW#GEDqz9zWC1kDRiJNPKvP2UxS6jtFjWMpucitrbn2ZC88" width="800" height="600" frameborder="0" allowfullscreen></iframe>
  </div>
</template>

<style scoped>

</style>