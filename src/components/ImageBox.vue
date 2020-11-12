<template>
    <div class="box">
        <img class="image" :src="source">
    </div>
</template>

<script>
export default {
  name: 'ImageBox',
  props: {
      source: String
  }
}
</script>

<style scoped>
    .box {
        margin: 0.2rem;
        padding: 0.2rem;
    }
    .image {
        border-radius: 0.1rem;
        width: 10rem;
        height: 10rem;
    }
</style>
