<template>
  <header>
    <h1>{{ title }}</h1>
    <Button_tracker text="Add Task" color="Green"></Button_tracker>
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