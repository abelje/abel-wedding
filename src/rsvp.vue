<script setup>
  import SectionHeader from "@/components/sectionHeader.vue";

  import { ref } from 'vue'
  import { useField, useForm } from 'vee-validate'

  const { handleSubmit, handleReset } = useForm({
    validationSchema: {
      name (value) {
        if (value?.length >= 2) return true

        return 'Name needs to be at least 2 characters.'
      },
      people (value) {
        if (/^[0-9-]$/.test(value)) return true

        return 'Amount of people needs to be 1 digit.'
      },
      email (value) {
        if (/^[a-z.-]+@[a-z.-]+\.[a-z]+$/i.test(value)) return true

        return 'Must be a valid e-mail.'
      }
    },
  })
  const name = useField('name')
  const people = useField('people')
  const email = useField('email')
  const select = useField('select')

  const submit = handleSubmit(values => {
    alert(JSON.stringify(values, null, 2))
  })
</script>

<template>
  <SectionHeader
      title="RSVP"
      subtitle="Tell us that you are coming to our wedding. We are excited to have you!"
  />
  <form @submit.prevent="submit">
    <v-text-field
        v-model="name.value.value"
        :counter="10"
        :error-messages="name.errorMessage.value"
        label="Name"
    ></v-text-field>

    <v-text-field
        v-model="people.value.value"
        :counter="7"
        :error-messages="people.errorMessage.value"
        label="Amount of People"
    ></v-text-field>

    <v-text-field
        v-model="email.value.value"
        :error-messages="email.errorMessage.value"
        label="E-mail"
    ></v-text-field>

    <v-btn
        class="me-4"
        type="submit"
    >
      submit
    </v-btn>

    <v-btn @click="handleReset">
      clear
    </v-btn>
  </form>
</template>

<style scoped>

</style>