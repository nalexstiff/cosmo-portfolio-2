<script setup>
import SiteHeader from './components/SiteHeader.vue'
import PageSection from './components/PageSection.vue'
import SiteFooter from './components/SiteFooter.vue'

const images = [
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
        src: "/artwork/potion props.jpg",
        alt: "Drawings of assorted bottles, candles and other items."
    },
    {
        src: "/artwork/treasure paint.jpg",
        alt: "A painting of a large treasure chest in a vast dungeon hall, surrounded by piles of gold. A skeleton sits leaning against the right side of the chest clutching at a sword between its ribs."
    },
    {
        src: "/artwork/creek 3.jpg",
        alt: "A drawing of a Victorian cottage next to a willow tree in the woods, with a creek running through the foreground to the left."
    },
    {
        src: "/artwork/creek kit.jpg",
        alt: "Drawings of assorted trees, rocks and shrubs."
    }
]
</script>

<template>
    <SiteHeader />
    <div class="gallery-section">
        <div class="gallery">
            <h1>Backgrounds</h1>
            <img class="gallery-image" v-for="image in images" :src="image.src" :alt="image.alt" />
        </div>
    </div>
    <SiteFooter></SiteFooter>
</template>

<style scoped>
.gallery-image {
    width: 100%;
    margin-bottom: 60px;
    border-style: solid;
    border-width: 4px;
}

.gallery-section {
    width: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
    background-color: #e0e0e0;
}

.gallery {
    width: 1540px;
    margin: 80px;
}

.gallery h1 {
    margin-left: 140px;
}

@media only screen and (max-width: 1080px) {
    .gallery h1 {
        margin-left: 60px;
    }
    .gallery {
        margin: 40px;
    }
}

@media only screen and (max-width: 760px) {
    .gallery {
        width: 100%;
        margin: 0px;
    }
    .gallery h1 {
        margin-left: 32px;
    }
    .gallery-image {
        border-style: none;
    }
}
</style>
