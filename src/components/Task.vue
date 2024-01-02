<template>
    <li>
        <div><slot></slot>  {{ i }}</div>
        <small>{{ task.dueDate }} @ {{ task.dueTime }}</small>
        <button @click="deleteTask(i)">X</button>
    </li>
</template>

<script>
export default {
    props: ['task', 'i']
}
</script>

<style>

</style>