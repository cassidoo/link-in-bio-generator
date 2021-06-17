<template>
  <div class="generate-button">
    <a>Generate my site</a>
    VITE_NAME={{ name }} <br />
    VITE_PROFILE_PIC={{ propic }}
    <br />
    booger
    {{ convertListOfLinks }}
  </div>
</template>

<script>
export default {
  name: 'GenerateButton',
  props: {
    name: String,
    propic: String,
    list: Array,
  },
  methods: {
    convertLink(str) {
      return `VITE_${str.replace(' ', '_').toUpperCase()}_LINK`
    },
    convertListOfLinks() {
      let linkString = ''
      console.log(this.list)

      this.list.forEach((l) => {
        linkString += `${convertLink(l.name)}=${l.url}&`
      })

      return linkString
    },
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
.generate-button {
  border: 3px solid black;
}
</style>
