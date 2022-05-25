<template>
  <div class="container">
    <Header_tracker title="Task Tracker"></Header_tracker>
    <AddTask></AddTask>
    <Tasks_tracker @toggle-reminder="toggleReminder" @delete-task="deleteTask" :tasks="tasks"></Tasks_tracker>
  </div>
</template>

<script>
import Header_tracker from "@/components/Header_tracker";
import Tasks_tracker from "@/components/Tasks_tracker";
import AddTask from "@/components/AddTask";

export default {
  name: 'App',
  components: {
    Header_tracker,
    Tasks_tracker,
    AddTask
  },
  data() {
    return {
      tasks: []
    }
  },
  methods: {
    deleteTask(id) {
      if (confirm("Are you sure to delete this item?")) {
        this.tasks = this.tasks.filter((task) => task.id !== id)
      }
    },
    toggleReminder(id) {
      this.tasks = this.tasks.map((task) => task.id === id ? {...task, reminder: !task.reminder} : task)
    }
  },
  created() {
    this.tasks = [
      {
        id: 1,
        text: 'Doctor appoinment',
        day: '23 May 2022',
        reminder: true
      },
      {
        id: 2,
        text: 'Have to go to market',
        day: '24 May 2022',
        reminder: true
      },
      {
        id: 3,
        text: 'Car repairing',
        day: '25 May 2022',
        reminder: false
      }
    ]
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400&display=swap');

* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: 'Poppins', sans-serif;
}

.container {
  max-width: 500px;
  margin: 30px auto;
  overflow: auto;
  min-height: 300px;
  border: 1px solid steelblue;
  padding: 30px;
  border-radius: 5px;
}

.btn {
  display: inline-block;
  background: #000;
  color: #fff;
  border: none;
  padding: 10px 20px;
  margin: 5px;
  border-radius: 5px;
  cursor: pointer;
  text-decoration: none;
  font-size: 15px;
  font-family: inherit;
}

.btn:focus {
  outline: none;
}

.btn:active {
  transform: scale(0.98);
}

.btn-block {
  display: block;
  width: 100%;
}
</style>
