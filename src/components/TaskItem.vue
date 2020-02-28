<template>
    
            <tr>
                <td>{{todo.todo}}</td>
                <td>{{todo.todoDate}}</td>
                <td>{{todo.address}}</td>
                <td><slot></slot></td>
            </tr>
        
</template>

<script>
    export default{
        props:["todo"]
    }
</script>

<style lang="scss">
    @import "../../variables.scss";

td {
   text-align: center;
}
</style>
