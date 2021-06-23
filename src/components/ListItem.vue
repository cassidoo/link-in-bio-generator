<template>
  <div class="item">
    <!--{{ item.name }} - {{ item.url }}-->
    <input type="text" v-model="item.name" />
    <input type="text" v-model="item.url" />
    <button @click="$emit('delete')">×</button>
  </div>
</template>

<script>
export default {
  name: 'ListItem',
  props: {
    item: Object,
  },
}

/**
VITE_PROFILE_PIC=https://github.com/cassidoo.png
VITE_NAME="Cassidy Williams"
VITE_GITHUB_LINK=https://github.com/cassidoo
VITE_TWITTER_LINK=https://twitter.com/cassidoo
VITE_MY_PERSONAL_WEBSITE=https://cassidoo.co
 */
</script>

<style scoped>
.item {
  margin: 5px;
}
</style>
