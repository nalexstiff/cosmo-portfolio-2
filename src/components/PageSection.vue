<script setup>
defineOptions({
    inheritAttrs: false
})

</script>

<template>
    <div class="section" v-bind="$attrs">
        <div class="section-content" :width="$attrs.width">
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
