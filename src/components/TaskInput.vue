<template>
  <div>
    <input type="text" class="input" v-model="task" @keyup.enter="addTask" />
  </div>
</template>

<script>
export default {
  data() {
    return {
      task: ""
    };
  },
  methods: {
    addTask() {
      this.$emit("taskAdded", this.task);
      this.task = "";
    }
  }
};
</script>

<style lang="scss" scoped>
@import "../../variables.scss";

.input {
  width: 100%;
  padding: 8px 10px;
  border: 1px solid $vue-blue;
}
</style>
