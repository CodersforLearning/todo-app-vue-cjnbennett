<template>
  <div id="app">
    <h1>Todo App</h1>
    <hr>
    <div class="task-container">
      <Task v-for="(task, index) in tasks" :key="task" :task="task" :index="index"/>
    </div>
    <hr>
    <div class="task">
        <h3 class="task-heading" contenteditable="true" id="new-task-heading">{{default_task_heading}}</h3>
        <hr>
        <strong>Description:</strong><br/>
        <div contenteditable="true" id="new-task-description">
        {{default_task_description}}
        </div>
        <div class="control-buttons">
          <button class="add-task-button" @click="addTask()">Add Task</button>
        </div>
      </div>
  </div>
</template>

<script>
import Task from './components/Task.vue';

export default {
  name: 'App',
  components: {
    Task
  },
  data() {
    return {
      tasks: [],
      default_task_heading: 'New Task',
      default_task_description: 'Enter description for new task.'
    };
  },
  methods: {
    addTask() {
      let heading = document.getElementById('new-task-heading');
      let description = document.getElementById('new-task-description');
      this.tasks.push({ name: heading.innerText, description: description.innerText });
      heading.innerText = this.default_task_heading;
      description.innerText = this.default_task_description;
    },
    deleteTask(index) {
      this.tasks.splice(index, 1);
    },
    completeTask(index) {
      document.getElementsByClassName('task')[index].className = 'task completed';
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

body {
  background-color: #111111;
}

.task-container {
  min-height: 250px;
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  justify-content: center;
}

.task {
  height: 150px;
  width: 200px;
  margin: 10px;
  background-color: lightgoldenrodyellow;
  text-align: left;
  font-size: 12px;
  padding: 5px;
  position: relative;
}

.completed {
  text-decoration: line-through;
  text-decoration-thickness: 3px;
  text-decoration-color: red;
}

.task-heading {
  color: #000000;
  margin-top: 10px;
  margin-bottom: -5px;
  text-align: center;
  font-size: 20px;
}

.control-buttons {
  display: flex;
  justify-content: space-evenly;
  position: absolute;
  bottom: 5px;
  left: 0px;
  right: 0px;
}
</style>
