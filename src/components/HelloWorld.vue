<template>
  <h1>{{ msg }}</h1>

  <p>
    <a href="https://vitejs.dev/guide/features.html" target="_blank"> Vite Documentation </a>
    |
    <a href="https://v3.vuejs.org/" target="_blank">Vue 3 Documentation</a>
  </p>

  <button type="button" @click="state.count++">count is: {{ state.count }}</button>
  <p>
    Edit
    <code>components/HelloWorld.vue</code> to test hot module replacement.
  </p>
</template>

<script setup>
import { defineProps, reactive } from 'vue'

defineProps({
  msg: String,
})

const state = reactive({ count: 0 })

/**
VITE_PROFILE_PIC=https://github.com/cassidoo.png
VITE_NAME="Cassidy Williams"
VITE_GITHUB_LINK=https://github.com/cassidoo
VITE_TWITTER_LINK=https://twitter.com/cassidoo
VITE_MY_PERSONAL_WEBSITE=https://cassidoo.co
 */
</script>

<style scoped>
a {
  color: #42b983;
}
</style>
