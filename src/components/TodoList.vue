<template>
  <ul>
    <task-item v-for="(todo, index) in todos" :todo="todo" :key="index">
      <button @click="$emit('taskDeleted', index)">X</button>
    </task-item>
  </ul>
</template>

<script>
import TaskItem from "./TaskItem";

export default {
  props: ["todos"],
  components: {
    TaskItem
  }
};
</script>

<style lang="scss">
</style>
