<template>
    <div @dblclick="$emit('toggle-reminder', task.id)" :class="[task.reminder ? 'reminder' : '', 'single-task']">
        <h3>{{ task.text }}</h3>
        <span>{{ task.day }}</span>
        <button @click="$emit('delete-task', task.id)">Remove</button>
    </div>
</template>

<script>
export default {
    name: 'Task',
    props: {
        task: Object
    },
}
</script>

<style scoped>
    .reminder{
        border-left: 3px solid green;
    }
    .single-task{
        padding: 20px 20px;
        margin: 5px 0px;
        font-family: 'Mukta', sans-serif;
        cursor: default;
        display: grid;
        grid-template-columns: auto 90px;
    }
    h3{
        margin: 0px;
    }
    button{
        grid-row: 1/3;
        grid-column: 2/3;
        height: 40px;
        align-self: center;
        color: white;
        font-family: 'Mukta', sans-serif;
        background: red;
        border: none;
        text-transform: uppercase;
    }
</style>