<script setup>

const props = defineProps({
    imgSrc: String,
    imgAlt: String,
    open: Boolean
})

</script>

<template>
    <div class="lb-background" :style="{visibility: $props.open ? 'visible' : 'hidden'}">
        <img src="/assets/closeX.svg" id="lb-close" @click="$emit('close')" />
        <div class="slideshow">
            <img src="/assets/leftArrow.svg" class="lb-arrow" id="lb-left" @click="$emit('prevImg')" />
            <img :src="$props.imgSrc" :alt="$props.imgAlt" class="lb-image" />
            <img src="/assets/rightArrow.svg" class="lb-arrow" id="lb-right" @click="$emit('nextImg')" />
        </div>
    </div>
</template>

<style>
.lb-background {
    z-index: 1500;
    width: 100%;
    height: 100%;
    position: fixed;
    top: 0;
    left: 0;
    background-color: rgba(0,0,0,0.7);
}

.slideshow {
    height: 100%;
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin: 0 40px 0 40px;
}

#lb-close {
    position: absolute;
    top: 40px;
    right: 40px;
    width: 80px;
    height: 80px;
    cursor: pointer;
}

.lb-image {
    max-width: 80%;
    max-height: 90%;
}

.lb-arrow {
    width: 80px;
    height: 120px;
    cursor: pointer;
}

</style>
