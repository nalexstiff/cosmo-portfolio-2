<script setup>
import { computed } from "vue"

const props = defineProps(["imgSrc", "linkUrl"])

const bgImg = computed(() => {
    return 'url("' + props["imgSrc"] + '")'
})
</script>

<template>
    <div class="tile" :style="{ backgroundImage: bgImg }">
        <h2 class="tile-text">
            <slot></slot>
        </h2>
    </div>
</template>

<style scoped>
.tile {
    margin: 20px 0 20px 0;
    width: 840px;
    height: 560px;
    display: flex;
    justify-content: center;
    align-items: center;
}

.tile-text {
    color: #3f3f3f;
    font-size: 72pt;
}

</style>
