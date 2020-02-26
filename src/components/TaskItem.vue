<template>
    <li>
        {{todo}}
        <slot></slot>
    </li>
    
</template>

<script>
    export default{
        props:["todo"]
    }
</script>

<style lang="scss">
</style>
