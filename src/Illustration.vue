<script setup>
import SiteHeader from './components/SiteHeader.vue'
import PageSection from './components/PageSection.vue'
import SiteFooter from './components/SiteFooter.vue'

const images = [
    {
        src: "/artwork/eye-and-the-needle.jpg",
        alt: "A portrait in profile on the right, looking toward a mountain in the background."
    },
    {
        src: "/artwork/guitar practice.jpg",
        alt: "A stylized figure holding an electric guitar."
    },
    {
        src: "/artwork/phases.jpg",
        alt: "A photo-collage showing phases of the moon imposed over choppy waves."
    },
    /*
    {
        src: "/artwork/.jpg",
        alt: ""
    },
    */
]
</script>

<template>
    <SiteHeader />
    <PageSection content-width="1000px" content-margin="80px">
        <div class="gallery">
            <h1>Illustration</h1>
            <p> Miscellaneous illustrations other than my background layouts. </p>
            <img class="gallery-image" v-for="image in images" :src="image.src" :alt="image.alt" />
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
