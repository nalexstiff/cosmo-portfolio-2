<script setup>
import { computed } from "vue"

const props = defineProps(["imgSrc", "linkUrl"])

const bgImg = computed(() => {
    return 'url("' + props["imgSrc"] + '")'
})
</script>

<template>
    <a :href="props['linkUrl']" class="tile" :style="{ backgroundImage: bgImg }">
        <h2 class="tile-text">
            <slot></slot>
        </h2>
    </a>
</template>

<style scoped>
.tile {
    display: block;
    margin: 20px auto 20px auto;
    width: 840px;
    height: 560px;
    display: flex;
    justify-content: center;
    align-items: center;
    text-decoration: none;
    color: #3f3f3f;
}
.tile:hover {
    text-decoration: underline;
}
.tile-text {
    color: #3f3f3f;
    font-size: 72pt;
}
@media only screen and (max-width: 1080px) {
    .tile {
        width: 600px;
        height: 400px;
    }
}
@media only screen and (max-width: 760px) {
    .tile {
        width: 100%;
        height: 66vw;
    }
    .tile-text {
        font-size: 64pt;
    }
}
@media only screen and (max-width: 540px) {
    .tile-text {
        font-size: 42pt;
    }
}

</style>
