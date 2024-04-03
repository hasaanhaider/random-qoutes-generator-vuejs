<script setup>
import { ref, onMounted } from 'vue'

const qoutes = ref([
  {
    text: 'This is the first qoute',
    author: 'Auth 1'
  },
  {
    text: 'This is the seconde qoute',
    author: 'Auth 2'
  },
  {
    text: 'This is the third qoute',
    author: 'Auth 3'
  }
])

const currentQoute = ref({ text: '', author: '' })
const getRandomQoute = () => {
  const randomIndex = Math.floor(Math.random() * qoutes.value.length)
  currentQoute.value = qoutes.value[randomIndex]
}

onMounted(getRandomQoute)
</script>

<template>
  <div class="container">
    <h1>Generate Random Qoute</h1>

    <div class="qoutes">
      <p class="qoutes-info">{{ currentQoute.text }}</p>
      <p class="author">{{ currentQoute.author }}</p>
    </div>

    <button class="btn-qoute" @click="getRandomQoute">Generate Qoute</button>
  </div>
</template>

<style scoped>
.container {
  width: 500px;
  margin: 20px auto;
  text-align: center;
  box-shadow: rgba(0, 0, 0, 0.24) 0px 3px 8px;
  padding: 20px;
}
.qoutes {
  background-color: rgb(245, 245, 245);
  padding: 60px;
  font-family: Impact, Haettenschweiler, 'Arial Narrow Bold', sans-serif;
  border-radius: 10px;
}
.btn-qoute {
  padding: 10px 20px;
  margin: 10px;
  background-color: blueviolet;
  border: white solid 1px;
  color: whitesmoke;
  border-radius: 8px;
}
</style>
