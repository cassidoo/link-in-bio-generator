<template>
  <div class="list">
    <p>Add a link: </p>
    <input type="text" v-model="newItem.name" id="name" />
    <input type="text" v-model="newItem.url" @keyup.enter="addItem" />
    <button @click="addItem">+</button>

    <ListItem v-for="(item, index) in list" :key="index" :item="item" @delete="removeItem(index)" />
  </div>
</template>

<script>
import ListItem from './ListItem.vue'

export default {
  name: 'Link',
  components: {
    ListItem,
  },
  data() {
    return {
      newItem: { name: '', url: 'https://' },
    }
  },
  props: {
    list: {
      type: Array,
      default: () => [],
    },
  },
  methods: {
    addItem() {
      this.$emit('update:list', [...this.list, this.newItem])
      this.newItem = { name: '', url: 'https://' }
      document.getElementById('name').focus()
    },
    removeItem(index) {
      this.list.splice(index, 1)
    },
  },
}
</script>

<style>
.list {
  padding: 20px;
}
input {
  padding: 5px;
}
</style>
