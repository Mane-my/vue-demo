<script>
export default {
  data() {
    return {
      value: '',
      isEmailValid: false
    }
  },

  methods: {
    promptField() {
      let value = prompt('Verify email')
      if (!value) {
        this.isEmailValid = false
        return
      }
      value = value.trim()
      this.value = value
      let isValid = this.checkEmailValid(value)
      this.isEmailValid = isValid
    },

    checkEmailValid(value) {
      return /^\w+([\.-]?\w+)*@\w+([\.-]?\w+)*(\.\w{2,3})+$/.test(value)
    },

    resetValues() {
      this.value = ''
    }
  }
}
</script>

<template>
  <header>
    <div class="btns">
      <button @click="promptField(value)">Input email</button>
      <button @click="resetValues()">Reset</button>
    </div>

    <div v-if="value">
      <h1 class="validField" v-if="isEmailValid">{{ value }}</h1>
      <h1 class="invalidField" v-else>{{ value }}</h1>

      <h4>{{ `Email is ${isEmailValid ? 'valid' : 'invalid'}` }}</h4>
    </div>
  </header>
</template>

<style scoped>
.btns button {
  cursor: pointer;
  color: #989898;
  font-size: 20px;
  padding: 10px;
  margin: 5px;
  border: 1px solid hsla(160, 100%, 37%, 1);
  border-radius: 10px;
  background-color: transparent;
}

.btns button:hover {
  background-color: hsla(160, 100%, 37%, 1);
  color: aliceblue;
}

.validField,
.invalidField {
  border-radius: 10px;
  color: aliceblue;
  text-align: center;
  margin-top: 20px;
  padding-bottom: 7px;
}

.validField {
  border: 1px solid green;
}

.validField h4 {
  color: green;
}

.invalidField {
  border: 1px solid red;
}

.invalidField h4 {
  color: red;
}
</style>
