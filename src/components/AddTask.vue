<template>
    <form @submit="onSubmit" class="add-form">
        <div class="form-control">
            <label>Task</label>
            <input type="text" v-model="text" name="text" placeholder="Add Task" />
        </div>

        <div class="form-control">
            <label>Day & Time</label>
            <input type="text" v-model="day" name="day" placeholder="Add Day & Time" />
        </div>

        <div class="form-control form-control-check">
            <label>Set Reminder</label>
            <input type="checkbox" v-model="reminder" name="reminder" />
        </div>

        <input type="submit" value="Save Task" class="btn btn-block" />
    </form>
</template>

<script>
export default {
    name: 'AddTask',
    data() {
        return {
            text: '',
            day: '',
            reminder: false
        }
    },
    methods: {
        onSubmit(e) {
            e.preventDefault()

            if(!this.text) {
                alert('Please add a task')
                return
            }

            const newTask = {
                // id: Math.floor(Math.random() * 10000),
                text: this.text,
                day: this.day,
                reminder: this.reminder
            }

            this.$emit('add-task', newTask)

            this.text = ''
            this.day = ''
            this.reminder = false
        }
    }
}
</script>

<style scoped>
form{
    padding: 40px 0px;
}
.form-control{
    display: grid;
    grid-template-columns: 100px auto;
    margin-bottom: 10px;
    font-family: 'Mukta', sans-serif;
}
input, input::placeholder{
    font-family: 'Mukta', sans-serif;
}
input[type=submit]{
    width: 100%;
    height: 30px;
    background-color: black;
    outline: none;
    color: white;
    text-transform: uppercase;
    border: none;
}
</style>