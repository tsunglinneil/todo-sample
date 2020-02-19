<template>
  <div id="app">
    <h1>Todo App</h1>
    <task-input @taskAdded="taskAdded"></task-input>
    <todo-list :todos="todos" @taskDeleted="taskDeleted"></todo-list>
  </div>
</template>

<script>
import TaskInput from "./components/TaskInput.vue";
import TodoList from "./components/TodoList.vue";

export default {
  data: function() {
    return {
      todos: ["First task"]
    };
  },
  components: {
    TaskInput,
    TodoList
  },
  methods: {
    taskAdded(task) {
      if (task) {
        this.todos.push(task);
      }
    },
    taskDeleted(index) {
      this.todos.splice(index, 1);
    }
  }
};
</script>

<style lang="scss">
@import "./variables.scss";

// *, *::before, *::after {
// 	box-sizing: border-box;
// }

#app {
  max-width: 400px;
  margin: 0 auto;
  line-height: 1.4;
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: $vue-blue;
}

h1 {
  text-align: center;
}
</style>
