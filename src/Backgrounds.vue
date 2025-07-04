<script setup>
import { ref } from "vue"

import SiteHeader from './components/SiteHeader.vue'
import PageSection from './components/PageSection.vue'
import SiteFooter from './components/SiteFooter.vue'
import Lightbox from './components/Lightbox.vue'

const images = [
    {
        src: "/artwork/fantasma-int-establishing-lines.jpg",
        alt: "An interior art deco cafe theater. We are looking from the screen toward a bar and seating area with a balcony above."
    },
    {
        src: "/artwork/fantasma-int-panorama-lines.jpg",
        alt: "An interior art deco cafe theater. We are at one end of the bar, looking at a fisheye panorama from the bar to the screen."
    },
    {
        src: "/artwork/fantasma-ext-establishing-lines.jpg",
        alt: "An exterior street. Old fashioned tree-lined American small town main street, with a shop, a small apartment building, a rowhouse and a large brick warehouse converted to a theater. The billboard sign on top reads FANTASMA."
    },
    {
        src: "/artwork/seaport overpass.jpg",
        alt: "An elevated street passing over another street in a Northeastern city, surrounded by midrise buildings with ornate brick facades."
    },
    {
        src: "/artwork/station 2.jpg",
        alt: "A drawing of an underground D.C. Metro station. A train platform with hexagonal tiles inside an arched concrete tunnel. A line of pylons with the word 'Bethesda' recede toward the end of the platform."
    },
    {
        src: "/artwork/crow house.jpg",
        alt: "A drawing of a block of rowhouses with an ornate Victorian house in the center. Skyscrapers rise behind the houses, and the scene is framed by a pair of tree trunks in the foreground.",
    },
    {
        src: "/artwork/potion paint 2.1.jpg",
        alt: "A painting of a potion bottle with a label reading \"Dont touch\" on a wooden background, surrounded by cluttered books, bottles, candles and other arcane implements."
    },
    {
        src: "/artwork/treasure paint.jpg",
        alt: "A painting of a large treasure chest in a vast dungeon hall, surrounded by piles of gold. A skeleton sits leaning against the right side of the chest clutching at a sword between its ribs."
    },
    {
        src: "/artwork/creek 3.jpg",
        alt: "A drawing of a Victorian cottage next to a willow tree in the woods, with a creek running through the foreground to the left."
    }
]

// code for handling lightbox events
const imgSrc = ref("")
const imgIndex = ref(0)
const imgAlt = ref("")
const lightboxVisible = ref(false)

function openLightbox (index) {
    console.log(index)
    imgIndex.value = index
    let image = images[index]
    imgSrc.value = image.src
    imgAlt.value = image.alt
    lightboxVisible.value = true
}

function closeLightbox () {
    lightboxVisible.value = false
}

function lightboxPrev () {
    let prevIndex = imgIndex.value - 1
    if (prevIndex < 0) {
        prevIndex = images.length - 1
    }
    openLightbox(prevIndex)
}

function lightboxNext () {
    let nextIndex = imgIndex.value + 1
    if (nextIndex >= images.length) {
        nextIndex = 0
    }
    openLightbox(nextIndex)
}

</script>

<template>
    <Lightbox :img-src="imgSrc" :img-alt="imgAlt" :open="lightboxVisible" @prev-img="lightboxPrev" @next-img="lightboxNext" @close="closeLightbox" />
    <SiteHeader />
    <PageSection content-width="1000px" content-margin="80px">
        <div class="gallery">
            <h1>Backgrounds</h1>
            <p> Animation background designs </p>
            <img class="gallery-image" v-for="(image, index) in images" :src="image.src" :alt="image.alt" @click="openLightbox(index)" />
        </div>
    </PageSection>
    <SiteFooter></SiteFooter>
</template>

<style scoped>
.gallery-image {
    width: 100%;
    margin-bottom: 60px;
    border-style: solid;
    border-width: 4px;
    cursor: pointer;
}

.gallery-section {
    width: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
    background-color: #e0e0e0;
}

@media only screen and (max-width: 760px) {
    .gallery-image {
        border-style: none;
    }
}
</style>
