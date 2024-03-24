<script setup>
import HelloWorld from './components/HelloWorld.vue'
// import TheWelcome from './components/TheWelcome.vue'
import { ref } from 'vue'

let count = ref(0)
function dectrementByTen() {
  count.value -= 10
}
function decrement() {
  count.value--
}
function increment() {
  count.value++
}
function incrementByTen() {
  count.value += 10
}

function resetCount() {
  count.value = 0
}
</script>

<template>
  <div class="counterBlock">
    <div class="count">{{ count }}</div>
    <div>
      <button @click="dectrementByTen()">-10</button>
      <button class="minus" @click="decrement()">-</button>
      <button class="plus" @click="increment()">+</button>
      <button @click="incrementByTen">+10</button>
    </div>
    <div>
      <button class="reset" @click="resetCount">Reset</button>
    </div>
  </div>

  <header>
    <img alt="Vue logo" class="logo" src="./assets/logo.svg" width="125" height="125" />

    <div class="wrapper">
      <HelloWorld msg="You did it!" />
    </div>
  </header>

  <!-- <main>
    <TheWelcome />
  </main> -->
</template>

<style scoped>
.counterBlock {
  text-align: center;
  margin-bottom: 30px;
}
.count {
  color: aliceblue;
  font-size: 25px;
}
button {
  cursor: pointer;
  color: #989898;
  font-size: 20px;
  padding: 5px;
  margin: 5px;
  border: 1px solid hsla(160, 100%, 37%, 1);
  border-radius: 10px;
  background-color: transparent;
}

.minus {
  padding: 5px 12px;
}
.plus {
  padding: 5px 10px;
}

button:hover {
  background-color: hsla(160, 100%, 37%, 1);
  color: aliceblue;
}

header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
