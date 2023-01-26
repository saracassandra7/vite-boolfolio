<script>
import axios from 'axios';
import ProjectCard from './components/ProjectCard.vue';

export default {
  name: 'App',
  components:{
    ProjectCard
  }, 

  data(){
    return{
      baseUrl: 'http://127.0.0.1:8000/api/',
      projects: []
    }
  },

  methods:{
    getApi(){
      axios.get(this.baseUrl + 'projects')
      .then(result=>{
        this.projects = result.data.projects;
        console.log(result.data.projects)
      })
      
    }
  },

  mounted(){
    this.getApi();
  }
}

</script>
  

<template>
<h1 class="text-center m-3">I miei progetti</h1>
<div class="container">
  <div class="row">
    <div class="col-4 mb-3" v-for="project in projects" :key="project.id">
      <ProjectCard :project="project"/>
    </div>
  </div>

</div>
</template>


<style lang="scss">
@use './style/general.scss';
</style>