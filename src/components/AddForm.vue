<template>
    <form @submit="addTask">
        <h3>Add Task</h3>
        <input type="text" v-model="task.name" placeholder="Task"/>
        <input type="text" v-model="task.day" placeholder="Day"/>
        <input type="submit" value="Add"/>



    </form>
</template>

<script>
export default {
    name:"AddForm",
    data(){
        return{
            task:{
                name:"",
                day:"",
            }
        }
    },
    props:{
        tasks:Array,
    },
    methods:{
        addTask(event){
            event.preventDefault();
            //never send state directly.. send a copy instead
            this.$emit('addTask',{...this.task,id:this.tasks.length>0?Math.max(...this.tasks.map(i=>i.id))+1:0})
        }
    }

}
</script>

<style scoped>
form{
    padding: 10px;
    background-color: salmon;
    display: flex;
    flex-direction: column;
    border-radius: 4px;
    margin-top:15px;

    
}
input{
    height:30px;
    margin-top:7px;
    border-radius: 4px;
    border:0px;
    padding: 6px;
}
input[type=submit]{
 background-color: rgb(24, 24, 24);
 color: blanchedalmond;
}
</style>