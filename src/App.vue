<script >
import axios from 'axios';
import ProjectCard from './components/ProjectCard.vue'

export default {
  name: "App",
  components: {
    ProjectCard
  },
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
  <div class="container">
    <h1 class="my-3 text-center">Ciao front-end</h1>
    <h3 class="text-center">Progetti:</h3>
    <div class="row">
      <div v-for="(elem, index) in projects" class="col-3 my-4">
        <ProjectCard :SingleCardData="elem" />
      </div>
    </div>
  </div>
</template>

<style lang="scss">
@use './style/main.scss';
</style>
