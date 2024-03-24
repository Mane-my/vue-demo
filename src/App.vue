<script setup>
import HelloWorld from './components/HelloWorld.vue'
import TheWelcome from './components/TheWelcome.vue'
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
  <div>
    <div>{{ count }}</div>
    <div>
      <button @click="dectrementByTen()">-10</button>
      <button @click="decrement()">-</button>
      <button @click="increment()">+</button>
      <button @click="incrementByTen">+10</button>
    </div>
    <div>
      <button @click="resetCount">Reset</button>
    </div>
  </div>

  <header>
    <img alt="Vue logo" class="logo" src="./assets/logo.svg" width="125" height="125" />

    <div class="wrapper">
      <HelloWorld msg="You did it!" />
    </div>
  </header>

  <main>
    <TheWelcome />
  </main>
</template>

<style scoped>
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
