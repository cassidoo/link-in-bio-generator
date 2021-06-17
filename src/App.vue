<template>
  <h1>Generate a Link in Bio Site</h1>
  <div class="required">
    <p><span>Your name:</span> <input type="text" placeholder="Liz Lemon" v-model="name" /></p>
    <p>
      <span>Your profile picture:</span>
      <input type="text" placeholder="Profile pic URL" v-model="propic" />
    </p>
  </div>

  <List v-model:list="list" />
  <!-- this is magic -->

  <div>
    hellloooo

    {{ name }}
    {{ propic }}
    {{ list }}
    <GenerateButton :name="name" :propic="propic" :list="list" />
  </div>
</template>

<script>
import List from './components/List.vue'
import GenerateButton from './components/GenerateButton.vue'

export default {
  name: 'App',
  components: {
    List,
    GenerateButton,
  },
  data() {
    return {
      list: [
        {
          name: 'example',
          url: 'example.com',
        },
      ],
      name: '',
      propic: '',
    }
  },
  methods: {
    addItem() {
      this.list.push(this.newItem)
      this.newItem = {}
    },
    removeItem(index) {
      this.list.splice(index, 1)
    },
  },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.required {
  max-width: 500px;
  margin-left: auto;
  margin-right: auto;
}

.required p {
  display: flex;
  justify-content: space-between;
}
</style>
