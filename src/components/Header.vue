<template>
    <header>
        <h1>{{text}}</h1>
        <Button @toggle-add-task="$emit('toggle-add-task')"
        :showAddTask="showAddTask"
         :text="showAddTask ? 'Close':'Add Task'" :color="showAddTask ? 'red':'green'"/>
    </header>
</template>

<script>
import Button from './Button.vue'
    export default {
        name: 'Header',
        props:{
            text: String,
            showAddTask:Boolean
        },
        components:{
            Button
        }
    }
</script>

<style scoped>
header{
    display: flex;
    justify-content: space-between;
    margin-bottom: 20px;
}
</style>
