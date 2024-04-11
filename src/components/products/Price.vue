<script>
export default {
  props: {
    value: {
      type: String,
      required: true
    }
  }
}
</script>

<template>
  <div class="priceDiv">
    <div>{{ value }}</div>
  </div>
</template>

<style scoped>
.priceDiv {
  display: flex;
}
</style>
