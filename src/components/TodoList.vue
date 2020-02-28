<template>
        <div>
        <table class="table" rules="all">
            <tbody>
                <tr>
                    <th>代辦事項</th>
                    <th>日期</th>
                    <th>地點</th>
                    <th>刪除</th>
                </tr>
                <task-item v-for="(todo,index) in todos" :todo="todo" :key="index">
                <button @click= "$emit('deleteTodo',index)"><span style="color:red">X</span></button>
                </task-item>
            </tbody>
        </table>
        </div>
        
</template>

<script>
    import TaskItem from "./TaskItem.vue";

    export default{
        
        props:["todos"],
        components:{
            TaskItem
        }
    }
</script>

<style lang="scss">
@import "../../variables.scss";

.table {
   width: 75%;
    font-size: small;
    border: solid;
    margin-top: 10%;
}
</style>
