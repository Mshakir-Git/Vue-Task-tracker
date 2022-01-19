<template>
    <div>
       <span> {{task.name}}</span>
        <span>{{task.day}}
        <button @click="$emit('delete-task',{id:task.id})">x</button>
        </span>
    </div>
</template>

<script>
export default {
    name:"Task",
    props:{
        task:Object,
    },
    emits:["delete-task"],
}
</script>

<style scoped>
    div{
        padding: 10px;
        margin-bottom: 10px;
        display: flex;
        flex-direction: row;
        justify-content: space-between;
        align-items: center;
        background-color: rgba(255, 167, 157, 0.973);
        border-radius: 4px;
    }
    button{
        margin-left: 10px;
        border-radius: 3px;
        border:0px;
        background-color: rgb(255, 90, 72);

    }
</style>