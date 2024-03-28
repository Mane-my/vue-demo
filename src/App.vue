<script>
export default {
  data() {
    return {
      txtValid: '',
      txtInvalid: ''
    }
  },

  methods: {
    promptField(value) {
      value = prompt('Verify email')
      console.log(value)

      if (/^\w+([\.-]?\w+)*@\w+([\.-]?\w+)*(\.\w{2,3})+$/.test(value)) {
        this.txtValid = value
        this.txtInvalid = ''
      } else {
        this.txtInvalid = value
        this.txtValid = ''
      }
    },

    resetValues() {
      this.txtValid = ''
      this.txtInvalid = ''
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

    <div class="validField" v-if="txtValid">
      <h1>{{ txtValid }}</h1>
      <h4>Email is valid</h4>
    </div>

    <div class="invalidField" v-if="txtInvalid">
      <h1>{{ txtInvalid }}</h1>
      <h4>Email is invalid</h4>
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

.validField h1,
.invalidField h1 {
  border-radius: 10px;
  color: aliceblue;
  text-align: center;
  margin-top: 20px;
  padding-bottom: 7px;
}

.validField h1 {
  border: 1px solid green;
}

.validField h4 {
  color: green;
}

.invalidField h1 {
  border: 1px solid red;
}

.invalidField h4 {
  color: red;
}
</style>
