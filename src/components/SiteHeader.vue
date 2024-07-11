<script setup>
import { ref, computed, onMounted, onUnmounted } from 'vue'

const scroll = ref(0)

function handleScroll (event) {
    scroll.value = window.scrollY
}

onMounted(() => {
    window.addEventListener("scroll", handleScroll)
})
onUnmounted(() => {
    window.removeEventListener("scroll", handleScroll)
})

const navbarHeight = computed(() => {
    return scroll.value > 140 ? 90 : 230 - scroll.value
})

const signHeight = computed(() => {
    return 156 * ((140 - Math.min(scroll.value, 140)) / 140) + 100
})

const signMargin = computed(() => {
    return -10 * ((140 - Math.min(scroll.value, 140)) / 140) - 6
})

</script>

<template>
    <div class="navbar">
        <div class="navbar-background" :style="{ height: navbarHeight + 'px' }">
            <div class="navbar-contents">
                <div class="logo-container">
                    <img class="logo-img" src="/cosmonas-sign.png" :style="{ width: signHeight + 'px', height: signHeight + 'px', marginTop: signMargin + 'px' }" />
                </div>
                <div class="navlinks-container">
                    <a class="navlink">backgrounds</a>
                    <a class="navlink">video</a>
                    <a class="navlink">contact</a>
                    <a class="navlink">blog</a>
                </div>
            </div>
        </div>
        <div class="shadow"></div>
    </div>
</template>

<style scoped>
.navbar {
    position: sticky;
    top: 0;
}

.navbar-background {
    width: 100%;
    height: 230px;
    display: block;
    background-color: #e0e0e0;
}

.navbar-contents {
    margin: 0 120px 0 120px;
    height: 100%;
    display: flex;
    justify-content: space-between;
}

.navlinks-container {
    height: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
}

.navlink {
    display: inline-block;
    margin-left: 60px;
    font-size: 32pt;
}

.logo-container {
    height: 100%;
}

.logo-img {
    margin-top: -16px;
}

.shadow {
    content: "";
    display: block;
    width: 100%;
    height: 100px;
    background-image: linear-gradient(black, rgba(0,0,0,0));
    opacity: 0.2;
}
</style>
