<script setup>
import SiteHeader from './components/SiteHeader.vue'
import PageSection from './components/PageSection.vue'
import Tile from './components/Tile.vue'
import SiteFooter from './components/SiteFooter.vue'
</script>

<template>
    <SiteHeader />
    <!-- splash image goes here -->
    <PageSection>
        <p><em>Hello! My name is Alex Stiff.</em></p>
        <p>I'm an artist and designer in the Washington, D.C. area. I do animation background design and illustration, as well as video production, motion graphics and editing.</p>
        <p>Have a look around my site, or get in touch via email at nalexstiff@gmail.com.</p>
    </PageSection>
    <PageSection>
        <Tile>backgrounds</Tile>
        <Tile>video</Tile>
    </PageSection>
    <SiteFooter />
</template>

<style scoped>
</style>
