<script setup>
const props = defineProps(["contentWidth"])

</script>

<template>
    <div class="section">
        <div class="section-content" :style="{ width: contentWidth }">
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

.section-content {
    width: 840px;
    margin: 80px;
}
</style>
