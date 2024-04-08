<script>
import Name from './Name.vue'
import Price from './Price.vue'
import Description from './Description.vue'

export default {
  components: {
    Name,
    Price,
    Description
  },
  props: {
    fruit: {
      type: Object,
      required: true
    }
  }
}
</script>

<template>
  <div>
    <Name :value="fruit.name" />
    <Price :value="fruit.price" />
    <Description :value="fruit.description" />
  </div>
</template>
