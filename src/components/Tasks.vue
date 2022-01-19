<template>
    <div class="container">

        <Task :key="index" v-for="(task,index) in tasks" :task="task" @delete-task="$emit('delete-task',$event)" />

    </div>
</template>

<script>
import Task from "./Task.vue"

export default {
    name:"Tasks",
    props:{
        tasks:Array,
    },
    components:{
        Task,
    },
    emits:["delete-task"]
}
</script>
<style scoped>
    .container{
        margin-top: 20px;
        padding: 10px;
        height: 50vh;
        overflow: auto;
        border-radius: 4px;
        background-color: rgba(255, 255, 255, 0.363)
    }
</style>