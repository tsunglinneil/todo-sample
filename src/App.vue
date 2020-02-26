<template>
  <div id="app">
    <h1>Todo App</h1>
      <task-input-vue @addTodoLists="addTodoLists"></task-input-vue>
      <todo-list-vue @deleteTodo="deleteTodo" :todos="todos"></todo-list-vue>
  </div>
</template>

<script>
import TaskInputVue from "./components/TaskInput.vue";
import TodoListVue from "./components/TodoList.vue"
export default{
  data(){
    return {
      todos:["example first"]
    }
  },
  components:{
    TaskInputVue,
    TodoListVue
  },
  methods:{
    addTodoLists(todo){
      console.log(`addTodoList ${todo}`)
      let context = ''
      if(todo){
        if(this.todos.includes(todo)){
          context = '代辦事項重複,你確定要新增？'
          if(confirm(context)){
            this.todos.push(todo)
          }
        }else{
          this.todos.push(todo);
        }
      }else{
        context = '請輸入代辦事項'
        alert(context)
      }
      
    },
    deleteTodo(index){
      console.log(`deleteTodo${index}`)
      if(confirm(`你確定要清除此${this.todos[index]}筆代辦事項？`))
        this.todos.splice(index,1)
    }
  }
}
</script>

<style lang="scss">
@import "./variables.scss";

#app {
  max-width: 400px;
  margin: 0 auto;
  line-height: 1.4;
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: $vue-green;
  font-size: 20px;
}

h1 {
  text-align: center;
}
</style>
