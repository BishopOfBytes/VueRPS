<template>
    <div class="box">
        <span class="label"><slot></slot></span>
        <input class="input" type="text" name="inputValue" :value="defaultValue" @change="$emit('text-change', $event.target.value)">
    </div>
</template>

<script>
export default {
  name: 'InputBox',
  props: {
      defaultValue: {
          type: String,
          default: ''
      }
  }
}
</script>

<style scoped>
    .box {
        margin: 0.2rem;
        padding: 0.2rem;
    }
    .label {
        margin-right: 1rem;
    }
    .input {

    }
</style>
