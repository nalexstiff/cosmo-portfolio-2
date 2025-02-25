<script setup>
import SiteHeader from "./components/SiteHeader.vue"
import PageSection from "./components/PageSection.vue"
import SiteFooter from "./components/SiteFooter.vue"

</script>

<template>
    <SiteHeader />
    <PageSection content-width="1000px" content-margin="80px">
        <h1>Animation</h1>
        <p> See my hand-drawn, 3D and motion graphics animation </p>
        <div class="embed-container" height="56.25%">
            <iframe class="embed-content" src="https://www.youtube.com/embed/D6zpOQccGP0?si=1FbByWqFlwGgFhRG"></iframe>
        </div>
    </PageSection>
    <SiteFooter />
</template>

<style>
.embed-container {
    width: 100%;
    margin-bottom: 60px;
    position: relative;
    overflow: hidden;
}

.embed-container::after {
    display: block;
    content: "";
    padding-top: 56.25%;
}

.embed-content {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    border: 0;
}

</style>
