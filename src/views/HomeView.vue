<template>
  <div class="home">
    <h1>Home</h1>
    <div v-for="project in projects" :key="project.id">
      <SingleProject :project="project"></SingleProject>
    </div>


  </div>
</template>

<script>
import SingleProject from '../components/SingleProject'
// @ is an alias to /src

export default {
  data() {
    return{
      projects: []
    }
  },
  name: 'HomeView',
  components: {
    SingleProject,
    
  },
  mounted() {
    fetch("http://localhost:3000/projects")
    .then((response) => {
      return response.json();
    })
    .then((data) => {
      console.log(data);
      this.projects= data;
    })
  }
}
</script>
