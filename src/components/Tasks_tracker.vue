<template>
  <div v-for=" task in tasks " v-bind:key="task.id ">
    <Task_tracker :task="task"></Task_tracker>
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
    }
  }
</script>


<style>

</style>