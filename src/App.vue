<template>
    <div class="container">
        <Header @toggle-add-task="toggleAddTask" title="Task Tracker" :showAddTask="showAddTask" />
        <router-view :showAddTask="showAddTask"></router-view>
        <Footer />
    </div>
</template>

<script>
import Header from './components/Header'
import Footer from './components/Footer'

export default {
    name: 'App',
    components: {
        Header,
        Footer,
    },
    data() {
        return {
            showAddTask: false
        }
    },
    methods: {
      toggleAddTask() {
        this.showAddTask = !this.showAddTask
      }
    },
}
</script>

<style scoped>
.container{
    width: 380px;
    border: 2px solid grey;
    border-radius: 20px;
    padding: 30px;
    margin: 0 auto
}
</style>