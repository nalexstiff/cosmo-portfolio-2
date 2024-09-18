<script setup>
import SiteHeader from './components/SiteHeader.vue'
import PageSection from './components/PageSection.vue'
import Tile from './components/Tile.vue'
import SiteFooter from './components/SiteFooter.vue'
</script>

<template>
    <SiteHeader />
    <img class="splash-img" src="/artwork/station 2.jpg" />
    <PageSection style="background-color: #ebebeb;">
        <p><b>Hello! My name is Nathan Alexander Stiff.</b></p>
        <p>I'm an artist and designer in the Washington, D.C. area. I do animation background design and illustration, as well as video production, motion graphics and editing.</p>
        <p>Have a look around my site, or get in touch via email at nalexstiff@gmail.com.</p>
    </PageSection>
    <PageSection>
        <Tile imgSrc="/tiles/backgrounds.jpg" linkUrl="backgrounds.html">backgrounds</Tile>
        <Tile imgSrc="/tiles/video.jpg" linkUrl="video.html">video</Tile>
    </PageSection>
    <SiteFooter />
</template>

<style scoped>
.splash-img {
    width: 100%;
    margin-top: -8vw;
    display: block;
    position: relative;
    z-index: -1;
}
</style>
