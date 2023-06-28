<script >
import axios from 'axios';

export default {
  data() {
    return {
      projects: []
    }
  },
  mounted() {
    this.getProjects()
  },
  methods: {
    getProjects() {
      axios.get('http://127.0.0.1:8000/api/projects')
        .then(res => {
          console.log(res.data)
          this.projects = res.data.projects
        })
    }
  }
}


</script>

<template>
  <h1>Ciao front-end</h1>
  <div>
  </div>
</template>

<style lang="scss">
@use './style/main.scss';
</style>
