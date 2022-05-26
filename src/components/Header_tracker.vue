<template>
  <header>
    <h1>{{ title }}</h1>
    <Button_tracker @btn-click="$emit('toggle-add-task')"   :text="showAddTask ? 'Close' : 'Add Task'"
                    :color="showAddTask ? 'red' : 'green'"></Button_tracker>
  </header>
</template>


<script>
import Button_tracker from "@/components/Button_tracker";
export default {
  name: 'Header_tracker',

  components: {
    Button_tracker
  },

  props: {
    title: String,
    showAddTask: Boolean,
  }

}
</script>


<style scoped>
header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 20px;
}
</style>