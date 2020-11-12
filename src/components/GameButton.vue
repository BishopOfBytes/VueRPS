<template>
    <button class="button" @click="$emit('click')"><slot></slot></button>
</template>

<script>
export default {
  name: 'GameButton'
}
</script>

<style scoped>
    .button {
        font-family: 'Courier New', Courier, monospace;
        font-weight: bold;
        background-color: green;
        border: none;
        color: white;
        padding: 0.8rem 1.2rem;
        border-radius: 0.5rem;
        text-align: center;
        text-decoration: none;
        display: inline-block;
        font-size: 1.5rem;
    }
</style>
