<script setup>
import { ref, computed, onMounted, onUnmounted } from "vue"

const props = defineProps({
    // width and margin of the page section content in desktop layout
    contentWidth: String,
    contentMargin: String
})

const breakpointSmall = 760

const innerWidth = ref(0)

function handleResize (event) {
    innerWidth.value = window.innerWidth
}

onMounted(() => {
    window.addEventListener("resize", handleResize)
    innerWidth.value = window.innerWidth
})
onUnmounted(() => {
    window.removeEventListener("resize", handleResize)
})

const actualWidth = computed(() => {
    if (innerWidth.value > breakpointSmall) {
        return props.contentWidth
    } else {
        return "100%"
    }
})

const actualMargin = computed(() => {
    if (innerWidth.value > breakpointSmall) {
        return props.contentMargin
    } else {
        return "0"
    }
})

</script>

<template>
    <div class="section">
        <div class="section-content" :style="{ width: actualWidth, margin: actualMargin }">
            <slot></slot>
        </div>
    </div>
</template>

<style scoped>
.section {
    width: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
    background-color: #e0e0e0;
}

/*.section-content {
    width: 840px;
    margin: 80px;
}*/
@media only screen and (max-width: 760px) {
    .section-content {
        /*width: 100%;
        margin: 0px;*/
        padding: 20px;
    }
}
</style>
