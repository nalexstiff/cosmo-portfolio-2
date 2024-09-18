<script setup>

</script>

<template>
    <div class="section">
        <div class="section-content">
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
@media only screen and (max-width: 760px) {
    .section-content {
        width: 100%;
        margin: 0px;
        padding: 20px;
    }
}
</style>
