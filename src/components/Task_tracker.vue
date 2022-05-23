<template>
  <div v-for=" task in tasks " v-bind:key="task.id ">
    <h3>{{ task.text }}</h3>
  </div>
</template>


<script>
  export default {
    name: 'Task_tracker',
    props : {
      tasks: Array,
    },
  }
</script>


<style>

</style>