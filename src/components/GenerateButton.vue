<template>
  <div class="generate-button">
    <a :href="siteLink">Generate my site</a>
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
        this.convertListOfLinks()
      )
    },
  },
}
</script>

<style scoped>
.generate-button a {
  display: block;
  border: 3px solid #2c3e50;
  border-radius: 20px;
  max-width: 500px;
  padding: 5px;
  margin-top: 5px;
  margin-left: auto;
  margin-right: auto;
  text-decoration: none;
  color: #2c3e50;
  background: white;
}
.generate-button a:hover {
  background: #2c3e50;
  color: white;
}
</style>
