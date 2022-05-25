<template>
  <div v-for=" task in tasks " v-bind:key="task.id ">
    <Task_tracker @toggle-reminder="$emit('toggle-reminder', task.id)" @delete-task="$emit('delete-task', task.id)" :task="task"></Task_tracker>
  </div>
</template>

*
<script>
import Task_tracker from "@/components/Task_tracker";
  export default {
    name: 'Tasks_tracker',
    props : {
      tasks: Array,
    },
    components:{
      Task_tracker
    },
    emits: ['delete-task', 'toggle-reminder']
  }
</script>


<style>

</style>