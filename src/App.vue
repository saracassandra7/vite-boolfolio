<script>
import axios from 'axios';

export default {
  name: 'App',
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
<div v-for="project in projects" :key="project.id">
  <h3>{{project.name}}</h3>
</div>
</template>


<style lang="scss">
@use './style/general.scss';
</style>