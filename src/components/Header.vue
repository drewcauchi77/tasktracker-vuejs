<template>
    <header>
        <h1>{{ title }}</h1>
        <Button v-show="homePage"
            @btn-click="$emit('toggle-add-task')" :text="showAddTask ? 'Close' : 'Add task'" 
            :color="showAddTask ? 'red' : 'green'"/>
    </header>
</template>

<script>
import Button from './Button'

export default {
    name: 'Header',
    props: {
        title: String,
        showAddTask: Boolean
    },
    components: {
        Button
    },
    computed: {
        homePage() {
            if(this.$route.path === '/') {
                return true
            }else{
                return false
            }
        }
    }
}
</script>

<style scoped>
h1{
    font-family: 'Mukta', sans-serif;
    margin: 0px;
    text-transform: uppercase;
}
header{
    display: grid;
    grid-template-columns: auto 100px;
}
button{
    height: 50px;
    align-self: center;
    color: white;
    font-family: 'Mukta', sans-serif;
    text-transform: uppercase;
    border: 1px solid white;
    outline: none;
    cursor: pointer;
}
</style>