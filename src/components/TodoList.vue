<template>
    <ul>
        <task-item v-for="(todo,index) in todos" :todo="todo" :key="index">
            <button @click= "$emit('deleteTodo',index)"><span style="color:red">X</span></button>
        </task-item>
    </ul>
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
</style>
