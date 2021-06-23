<template>
  <h1>Generate a "Link in Bio" Site</h1>
  <div class="required">
    <p><span>Your name:</span> <input type="text" placeholder="Liz Lemon" v-model="name" /></p>
    <p>
      <span>Your profile picture:</span>
      <input type="text" placeholder="Profile pic URL" v-model="propic" />
    </p>
  </div>

  <List v-model:list="list" />

  <GenerateButton :name="name" :propic="propic" :list="list" />

  <p class="repos">
    <a href="https://test-lib-generated-stream-314.netlify.app/">Here's an example site</a>
    ·
    <a href="https://github.com/cassidoo/link-in-bio-generator">Here's the repo</a>
  </p>
  
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
          url: 'https://example.com',
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

h1 {
  font-weight: 900;
}

input {
  border-radius: 5px;
  height: 20px;
  margin: 0 5px;
}

button {
  margin: 0 5px;
  width: 30px;
  height: 30px;
  background: #2c3e50;
  border: 2px solid #2c3e50;
  border-radius: 50%;
  border: none;
  color: white;
  cursor: pointer;
  font-weight: bold;
  font-size: 16px;
}

button:hover {
  background: white;
  border: 2px solid #2c3e50;
  color: #2c3e50;
}

.repos a {
  color: #2c3e50;
}
</style>
