<script setup>
import { ref, computed, onMounted, onUnmounted } from "vue"

const breakpointMid = 1080

const scroll = ref(0)
const innerWidth = ref(0)

function handleScroll (event) {
    scroll.value = window.scrollY
}
function handleResize (event) {
    innerWidth.value = window.innerWidth
}

onMounted(() => {
    window.addEventListener("scroll", handleScroll)
    window.addEventListener("resize", handleResize)
    scroll.value = window.scrollY
    innerWidth.value = window.innerWidth
})
onUnmounted(() => {
    window.removeEventListener("scroll", handleScroll)
    window.removeEventListener("resize", handleResize)
})

const signHeight = computed(() => {
    if (innerWidth.value <= breakpointMid) {
        return 90
    }
    return 156 * ((140 - Math.min(scroll.value, 140)) / 140) + 100
})

const signMargin = computed(() => {
    if (innerWidth.value <= breakpointMid) {
        return 0
    }
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
.logo-img {
    height: 256px;
    margin-top: -90px;
    /*
    transition-property: width, height, margin-top;
    transition-duration: 0.2s;
    */
}
@media only screen and (max-width: 1080px) {
    .navbar-contents {
        margin-top: -190px;
    }
    .shadow {
        top: 90px;
    }
    .navbar-background-top {
        height: 0px;
    }
    .logo-img {
        height: 90px;
    }
}

.navlinks-container {
    height: auto;
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
    height: 90px;
}

@media only screen and (max-width: 760px) {
    .navbar-contents {
        flex-direction: column;
        height: auto;
        background-color: #e0e0e0;
        position: relative;
    }
    .navbar-background {
        position: relative;
    }
    .shadow {
        position: relative;
    }
    .navlinks-container {
        flex-direction: column;
        margin-right: 0px;
    }
    .logo-container {
        display: flex;
        justify-content: center;
    }
}

</style>
