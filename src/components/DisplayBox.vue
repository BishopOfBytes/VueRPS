<template>
    <div class="box">
        <span class="text">
            <slot></slot>
        </span>
    </div>
</template>

<script>
export default {
  name: 'DisplayBox'
}
</script>

<style scoped>
    .box {
        margin: 0.2rem;
        padding: 0.2rem;
    }
    .text {
        font-family: 'Courier New', Courier, monospace;
        font-size: 2rem;
    }
</style>
