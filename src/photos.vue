<script setup>
    import SectionHeader from "@/components/sectionHeader.vue";
    import {ref} from "vue";

    let images = ref([
        { url: "Favorites/DSCN1246.JPG.jpg" },
        { url: "Favorites/DSCN1097.JPG.jpg" },
        { url: "Favorites/DSCN1185.JPG.jpg" },
        { url: "Favorites/DSCN1206.JPG.jpg" },
        { url: "Favorites/DSCN1224.JPG.jpg" },
        { url: "Favorites/DSCN1250.JPG.jpg" },
        { url: "Favorites/DSCN1272.JPG.jpg" },
        { url: "Favorites/DSCN1276.JPG.jpg" },
        { url: "Favorites/DSCN1280.JPG.jpg" },
        { url: "Favorites/DSCN1287.JPG.jpg" },
        { url: "Edited/DSCN1259.JPG.jpg" },
        { url: "Edited/DSCN1085.JPG.jpg" }
    ])
</script>

<template>
    <SectionHeader
        title="Photos"
        subtitle="Help us to capture moments of our special day by uploading your photos to our album!"
    />

    <v-btn class="ma-4 bg-green-darken-2" href="https://photos.app.goo.gl/6u4BqKFx65DPGPt27">Google Photos</v-btn>
    <v-btn class="ma-4 bg-green-darken-2" href="https://albums.ente.io/?t=5VJCIENTQW#GEDqz9zWC1kDRiJNPKvP2UxS6jtFjWMpucitrbn2ZC88">Ente</v-btn>
    <v-divider></v-divider>
    <h1 class="text-center d-xs-block hidden-sm-and-up">Engagement Album</h1>
    <p class="text-center d-xs-block hidden-sm-and-up">Photos Taken By Elizabeth Davis</p>
    <div class="d-xs-flex hidden-sm-and-up justify-center ma-5">
        <v-carousel height="75vh">
            <v-carousel-item
                v-for="(item, index) in images"
                :key="index"
                :src="item.url"
                cover
            ></v-carousel-item>
        </v-carousel>
    </div>
    <v-divider class="d-xs-flex hidden-sm-and-up"></v-divider>
<!--    <h1 class="text-center">Wedding Day Ente Photo Album</h1>-->
<!--    <p class="text-center">Upload Photos by selecting the 'Ente' button up above. Thank you for contributing!</p>-->
<!--    <div class="d-flex justify-center ma-5">-->
<!--        &lt;!&ndash;  Use ente for embed code&ndash;&gt;-->
<!--        <iframe src="https://embed.ente.io/?t=5VJCIENTQW#GEDqz9zWC1kDRiJNPKvP2UxS6jtFjWMpucitrbn2ZC88" width="700" height="500" frameborder="0" allowfullscreen></iframe>-->
<!--    </div>-->
<!--    <v-divider class="d-none d-sm-flex hidden-xs"></v-divider>-->
<!--    <h1 class="text-center d-sm-block hidden-xs">Engagement Album</h1>-->
<!--    <p class="text-center d-sm-block hidden-xs">Photos Taken By Elizabeth Davis</p>-->
<!--    <div class="hidden-xs d-sm-flex ma-5">-->
<!--        <v-row>-->
<!--            <v-col-->
<!--                v-for="(item,n) in images"-->
<!--                :key="n"-->
<!--                class="d-flex child-flex"-->
<!--                cols="4"-->
<!--            >-->
<!--                <v-img-->
<!--                    :src="item.url"-->
<!--                    aspect-ratio="1"-->
<!--                    class="bg-grey-lighten-2"-->
<!--                    cover-->
<!--                >-->
<!--                    <template v-slot:placeholder>-->
<!--                        <v-row class="fill-height align-center justify-center">-->
<!--                            <v-progress-circular-->
<!--                                color="grey-lighten-5"-->
<!--                                indeterminate-->
<!--                            ></v-progress-circular>-->
<!--                        </v-row>-->
<!--                    </template>-->
<!--                </v-img>-->
<!--            </v-col>-->
<!--        </v-row>-->
<!--    </div>-->
</template>

<style scoped>

</style>