<script>
import Name from './Name.vue'
import Price from './Price.vue'
import Description from './Description.vue'

export default {
  components: {
    Name,
    Price,
    Description
  }
}
</script>

<template>
  <Name :value="name" />
  <Price :value="price" />
  <Description :value="description" />
  <div></div>
</template>
{/* fruits: [ { name: "apple", price: "3$"", description: "Golden apples from Armenia" }, { name:
"pear", price: "3.4$", description: "Sweet pears" }, { name: "cherry", price: "2.6$", description:
"Sour red cherries" }, { name: "lemon", price: "4$", description: "Big Chinese lemons" }, { name:
"banana", price: "3.7$", description: "Fresh bananas from Ecuador" }, ] */}
