<template>
    <div>
      <input class="input" type="text" @keyup.enter="addTodoList" v-model="todo" :placeholder="placeholder+todoinput">
      <input class="input" type="date" v-model='todoDate'>
      <input class="input" type="text" v-model="address" :placeholder="placeholder+addressinput">
      <button class="input" style="width: 75%" @click="addTodoList">送出</button>
    </div>
</template>

<script>
  export default{
    data(){
      return{
        todo:'',
        todoDate:'',
        address:'',
        placeholder:'請輸入',
        todoinput:'代辦事項',
        addressinput:'地點'
      };
    },
    methods:{
      addTodoList(){
        console.log(`add`)
        let errorMsg = '請輸入 '
        let newTodo = {}
        if(this.todo != '' && this.todoDate != '' && this.address != ''){
            newTodo = {
              todo:this.todo,
              todoDate:this.todoDate,
              address:this.address
            }
            this.$emit("addTodoLists",newTodo)
            this.todo = ''
            this.todoDate = ''
            this.address = ''
        }else{
          if(this.todo == '')
            errorMsg = errorMsg.concat(this.todoinput,' ')
          if(this.todoDate == '')
            errorMsg = errorMsg.concat('日期 ')
          if(this.address == '')
            errorMsg = errorMsg.concat(this.addressinput,' ')


          alert(errorMsg)
        }
        
        
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
  margin-top: 10px;
}
</style>
