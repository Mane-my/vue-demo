<script>
import Product from './components/products/Product.vue'

export default {
  components: {
    Product
  }
}
</script>

<template>
  <div>
    <Product {{name}} />
  </div>
</template>
