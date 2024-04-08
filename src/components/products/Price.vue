<script>
export default {
  props: {
    value: {
      type: String,
      required: true
    }
  },
  data() {
    return {
      priceValue: this.value,
      rate: 400,
      currency: 'USD'
    }
  },
  methods: {
    changeCurrency() {},
    onSubmit() {
      console.log(this.priceValue)
      this.$emit('submitName', this.priceValue)
      if (this.currency === 'USD') {
        this.currency = 'AMD'
        this.priceValue = this.value * this.rate

        console.log(this.priceValue, this.value)
      } else {
        this.currency = 'USD'
        this.priceValue = this.value / this.rate
      }
    }
  }
}
</script>

<template>
  <div class="priceDiv">
    <div @myFunc="clicked">{{ value }} {{ currency }}</div>
    <button @click="onSubmit">Change currency</button>
  </div>
</template>

<style scoped>
.priceDiv {
  display: flex;
}
</style>
