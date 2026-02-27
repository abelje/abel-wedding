<script setup>
  function date_countdown(){
    // June 5, 2027 - Current Date
    let currentDate = new Date();
    let wedding = new Date(2027, 5, 5);
    currentDate.setHours(0,0,0,0);
    let distance = wedding - currentDate;
    let days = Math.floor(distance / (1000 * 60 * 60 * 24));

    // include current day (round up to next day)
    return days + 1;
  }
  const countdown = date_countdown();
</script>

<template>
  <v-row>
    <v-col class="d-none d-md-flex">
      <v-img src="vine-flower.jpg" class="flower" width="20%" cover></v-img>
    </v-col>
    <v-col>
      <v-container class="d-flex justify-center">
        <v-img src="winterfest.jpg" class="border-solid" width="50%" style="margin-top: 5%"></v-img>
      </v-container>
      <h1 class="text-center">June 5, 2027 - Crete, IL</h1>
      <v-divider/>
      <h2 class="text-center">{{countdown}} days</h2>
      <br>
      <p class="text-center text-h5">Both of us are excited to share this special day with you! This is the one stop
        shop to get addresses, RSVP, access our registry, and upload photos of our special day!</p>
    </v-col>
    <v-col class="d-none d-md-flex justify-end">
      <v-img src="vine-flower.jpg" class="flower" width="20%" cover></v-img>
    </v-col>
  </v-row>
</template>

<style scoped>
  .flower {
    position: absolute;
  }
  .cedarville-cursive-regular {
    font-family: "Cedarville Cursive", cursive;
    font-weight: 400;
    font-style: normal;
    line-height: 1;
  }
</style>