<script setup>
import { ref } from 'vue'

const greeting = ref('Hello Vue Developer')
const increaseExcitement = () => {
  greeting.value += '!'
  if (greeting.value.endsWith('!!!!')) {
    imgSrc.value = 'https://media.giphy.com/media/2alKkyRFPKRSU/giphy.gif'
  }
}
const imgSrc = ref('https://media.giphy.com/media/wsXVAJY8ibkqBSmjEF/giphy.gif')
</script>

<template>
  <div>
    <h1>{{ greeting }}</h1>
    <button @click="increaseExcitement">More Excitement</button>
    <div v-if="greeting.endsWith('!!!!')">
      <h2>Ok, we're sufficiently excited!</h2>
    </div>
    <div v-else>
      <p>We're starting to get a little excited...</p>
    </div>
    <img :src="imgSrc" :alt="greeting.endsWith('!!!!') ? 'Excitement' : 'Anticipation'" />
  </div>
</template>

<style scoped></style>
