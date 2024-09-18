<script setup>
import { ref, computed, onMounted, onUnmounted } from "vue"

const scroll = ref(0)
/*
const signHeight = ref(256)
const signMargin = ref(-90)
*/

function handleScroll (event) {
    /*
    const newScroll = window.scrollY
    if (scroll.value == 0 && newScroll > 0) {
        signHeight.value = 90
        signMargin.value = -8
    }
    if (scroll.value > 0 && newScroll == 0) {
        signHeight.value = 256
        signMargin.value = -90
    }
    */
    scroll.value = window.scrollY
}

onMounted(() => {
    window.addEventListener("scroll", handleScroll)
    scroll.value = window.scrollY
})
onUnmounted(() => {
    window.removeEventListener("scroll", handleScroll)
})

const signHeight = computed(() => {
    return 156 * ((140 - Math.min(scroll.value, 140)) / 140) + 100
})

const signMargin = computed(() => {
    const interp = ((70 - Math.min(scroll.value, 70)) / 70)
    return -80 * interp - 8
})

</script>

<template>
    <div class="navbar-background-top"></div>
    <div class="navbar-background"></div>
    <div class="shadow"></div>
    <div class="navbar-contents">
        <a href="/index.html" class="logo-container">
            <img class="logo-img" src="/cosmonas-sign.png" :style="{ width: signHeight + 'px', height: signHeight + 'px', marginTop: signMargin + 'px' }" />
        </a>
        <div class="navlinks-container">
            <a class="navlink" href="/backgrounds.html">backgrounds</a>
            <a class="navlink" href="/video.html">video</a>
            <!--
            <a class="navlink" href="/contact.html">contact</a>
            <a class="navlink">blog</a>
            -->
        </div>
    </div>
</template>

<style scoped>
.navbar-background-top {
    height: 140px;
    width: 100%;
    background-color: #e0e0e0;
}
.navbar-background {
    position: sticky;
    top: 0;
    height: 90px;
    width: 100%;
    background-color: #e0e0e0;
}

.navbar-contents {
    position: sticky;
    top: 0;
    margin-top: -260px;
    padding: 0 120px 0 120px;
    height: 90px;
    display: flex;
    justify-content: space-between;
}

.navlinks-container {
    height: 100%;
    display: flex;
    margin-right: -30px;
    justify-content: center;
    align-items: center;
}

.navlink {
    display: inline-block;
    padding: 0 30px;
    font-family: "EB Garamond", "Times New Roman", serif;
    color: black;
    text-decoration: none;
    font-size: 32pt;
}

.navlink:hover {
    text-decoration: underline;
}

@keyframes logo-shrink {
    from {
        height: 256px;
        margin-top: -90px;
    }
    to {
        height: 90px;
        margin-top: -8px;
    }
}

.logo-container {
    display: block;
    height: 100%;
}

.logo-img {
    height: 256px;
    margin-top: -90px;
    /*
    transition-property: width, height, margin-top;
    transition-duration: 0.2s;
    */
}

.shadow {
    position: sticky;
    top: 90px;
    content: "";
    display: block;
    width: 100%;
    height: 100px;
    background-image: linear-gradient(black, rgba(0,0,0,0));
    opacity: 0.2;
}
</style>
