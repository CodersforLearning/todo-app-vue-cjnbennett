<template>
  <div id="app">
    <h1>Todo App</h1>
    <hr>
    <div class="task-container">
      <div class="task" v-for="n in 3" :key="n.value">
        <h3 class="task-heading">Task {{n}}</h3>
        <hr>
        <strong>Description:</strong><br/>
        This is a fun task! Task number {{n}}.
        <div class="control-buttons">
          <button class="completed-button">Mark Completed</button>
          <button class="delete-button">Delete Task</button>
        </div>
      </div>
    </div>
    <hr>
    <div class="task">
        <h3 class="task-heading" contenteditable="true">New Task</h3>
        <hr>
        <strong>Description:</strong><br/>
        <div contenteditable="true">
        Enter description for new task.
        </div>
        <div class="control-buttons">
          <button class="add-task-button">Add Task</button>
        </div>
      </div>
  </div>
</template>

<script>
export default {
  name: 'App'
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
  height: 250px;
  display: flex;
  flex-direction: row;
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
