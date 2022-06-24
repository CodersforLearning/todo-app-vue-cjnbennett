<template>
  <div class="task">
    <h3 class="task-heading">{{task.name}}</h3>
    <hr>
    <strong>Description:</strong><br/>
    {{task.description}}
    <div class="control-buttons">
      <button class="completed-button">Mark Completed</button>
      <button class="delete-button" @click="$parent.deleteTask(index)">Delete Task</button>
    </div>
  </div>
</template>

<script>

export default {
  name: 'TaskComponent',
  props: {
    task: {
        type: Object,
        required: true
    },
    index: {
        type: Number,
        required: true
    }
  }
}
</script>
