<script>
export default {
  name: 'ProjectCard',

  props:{
    project: Object
  }

}
</script>


<template>

<div class="card" style="width: 19rem;">
  <div class="card-body text-center">
    <h5 class="card-title">{{project.name}}</h5>
    <h6 class="card-subtitle mb-2 text-muted">Cliente: {{project.client_name}}</h6>
    <p class="card-text">Descrizione progetto: <br> {{project.summary}}</p>
  </div>
</div>
  
</template>


<style lang="scss" scoped>

</style>