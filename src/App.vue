<script>
import Product from './components/products/Product.vue'

export default {
  components: {
    Product
  },
  data() {
    return {
      fruits: [
        {
          name: 'apple',
          price: '3$',
          description: 'Golden apples from Armenia'
        },
        {
          name: 'pear',
          price: '3.4$',
          description: 'Sweet pears'
        },
        {
          name: 'cherry',
          price: '2.6$',
          description: 'Sour red cherries'
        },
        {
          name: 'lemon',
          price: '4$',
          description: 'Big Chinese lemons'
        },
        {
          name: 'banana',
          price: '3.7$',
          description: 'Fresh bananas from Ecuador'
        }
      ]
    }
  }
}
</script>

<template>
  <div>
    <Product v-for="fruit in fruits" :fruit="fruit" :key="fruit.name" />
  </div>
</template>
