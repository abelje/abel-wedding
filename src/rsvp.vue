<script setup>
import SectionHeader from "@/components/sectionHeader.vue";

import {ref} from "vue";
let people = ref(0)
</script>

<template>
  <SectionHeader
      title="RSVP"
      subtitle="Tell us that you are coming to our wedding. We are excited to have you!"
  />
  <h1>{{ people }} rsvped</h1>
  <iframe
      src="https://docs.google.com/forms/d/e/1FAIpQLSc4A4XYOetMNWCB8S3X696uB6j3qV0-WoQ9OXV9WKCai0-WRA/viewform?embedded=true"
      width="640" height="905" frameBorder="0" marginHeight="0" marginWidth="0">Loading…</iframe>
</template>

<style scoped>

</style>