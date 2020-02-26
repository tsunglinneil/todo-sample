<template>
    <div>
      <input class="input" type="text" @keyup.enter="addTodoList" v-model="todo" :placeholder="placeholder">
      <button class="input" style="width: 20%" @click="addTodoList">送出</button>
    </div>
</template>

<script>
  export default{
    data(){
      return{
        todo:'',
        placeholder:'請輸入代辦事項'
      };
    },
    methods:{
      addTodoList(){
        console.log(`add`)
        this.$emit("addTodoLists",this.todo)
        this.todo = ''
      }
    }
  }
</script>

<style lang="scss" scoped>
@import "../../variables.scss";

.input {
  width: 70%;
  border-radius: 10px;
  padding: 8px 10px;
  color: darkgreen;
  font-size: 20px;
  font-family: Arial, Helvetica, sans-serif;
  align-content: center;
}
</style>
