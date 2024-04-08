<script>
export default {
  data() {
    return {
      message: 'Hello World!',
      count: 0,
      myValue: ''
    }
  },
  methods: {
    changeTxt() {
      this.message = 'llll'
    },
    increment() {
      this.count++
    },
    getValue(event) {
      this.myValue = event.target.value
    }
  }
}
</script>

<template>
  <div @click="changeTxt()">{{ message }}</div>
  <div>{{ count }}</div>
  <button @click="increment">+</button>
  <br />

  <textarea type="text" @input="getValue"> </textarea>
  <div>{{ myValue }}</div>
</template>

<style scoped></style>
