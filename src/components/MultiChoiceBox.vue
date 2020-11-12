<template>
    <template v-for="item in options" :key="item">
        <button class="button" @click="$emit('click', item)">{{ item }}</button>
    </template>
</template>

<script>
export default {
  name: 'MultiChoiceBox',
  props: {
      options: Array // Array of titles ... ex: ['Rock', 'Paper', 'Scissors']
  }
}
</script>

<style scoped>
    .button {
        font-family: 'Courier New', Courier, monospace;
        font-weight: bold;
        background-color: green;
        border: none;
        color: white;
        margin: 0.5rem;
        padding: 0.8rem 1.2rem;
        border-radius: 0.5rem;
        text-align: center;
        text-decoration: none;
        display: inline-block;
        font-size: 1.5rem;
    }
</style>
