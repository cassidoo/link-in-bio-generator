<template>
  <div class="generate-button">
    <a :href="siteLink">Generate my site</a>

    VITE_NAME={{ name }} <br />
    VITE_PROFILE_PIC={{ propic }}
    <br />
    booger
    {{ convertListOfLinks() }}
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

      this.list.forEach((l) => {
        linkString += `${this.convertLink(l.name)}=${l.url}&`
      })

      return linkString
    },
  },
  computed: {
    siteLink() {
      return (
        'https://app.netlify.com/start/deploy?repository=https://github.com/cassidoo/link-in-bio-template#' +
        'VITE_NAME=' +
        this.name +
        '&' +
        'VITE_PROFILE_PIC=' +
        this.propic +
        '&' +
        this.convertListToLinks
      )
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
