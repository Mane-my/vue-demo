<script>
export default {
  data() {
    return {
      value: 0,
      rate: 400,
      currency: 'AMD'
    }
  },

  methods: {
    inputFunc(event) {
      this.value = event.target.value
    },
    focusFunc() {
      if (+this.value === 0) {
        this.value = ''
      }
    },
    changeCurrency() {
      if (this.currency === 'AMD') {
        this.currency = 'USD'
      } else {
        this.currency = 'AMD'
      }
      this.value = 0
    }
  }
}
</script>

<template>
  <div class="inputDiv" v-if="currency === 'AMD'">
    <div>
      <div>AMD -> USD</div>
      <input @input="inputFunc" @focus="focusFunc" type="number" :value="value" />
      <input type="number" disabled :value="value / rate" />
    </div>
    <button @click="changeCurrency">USD -> AMD</button>
  </div>

  <div class="inputDiv" v-else>
    <div>
      <div>USD -> AMD</div>
      <input @input="inputFunc" @focus="focusFunc" type="number" :value="value" />
      <input type="number" disabled :value="value * rate" />
    </div>
    <button @click="changeCurrency">AMD -> USD</button>
  </div>
</template>

<style scoped>
.inputDiv input {
  color: aliceblue;
  margin: 5px;
  padding: 5px;
  background: none;
  border: 1px solid hsla(160, 100%, 37%, 1);
  border-radius: 10px;
}

.inputDiv button {
  cursor: pointer;
  color: #989898;
  padding: 10px;
  margin: 5px;
  border: 1px solid hsla(160, 100%, 37%, 1);
  border-radius: 10px;
  background-color: transparent;
}

.inputDiv button:hover {
  background-color: hsla(160, 100%, 37%, 1);
  color: aliceblue;
}
</style>
