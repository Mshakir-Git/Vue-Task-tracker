<template>
  <div class="app">
  <Header title="Task Tracker" @toggle="toggleAddForm"/>
  <Tasks :tasks="tasks" @delete-task="deleteTask($event.id)" />
  <AddForm v-if="addForm" @add-task="addTask($event)" :tasks="tasks"/>
  </div>
</template>

<script>
import Header from "./components/Header.vue"
import Tasks from "./components/Tasks.vue"
import AddForm from "./components/AddForm.vue"


export default {
  name:"App",
  data(){
    return {
      tasks:[],
      addForm:true,
    }
  },
  components:{
    Header,
    Tasks,
    AddForm
  },
  methods:{
    addTask(task){
      console.log(task)

      this.tasks=[...this.tasks,task]
    },
    deleteTask(id){
      this.tasks=this.tasks.filter((t)=>t.id!=id)
    },
    toggleAddForm(){
      this.addForm=!this.addForm
    }
  },
  created(){
    this.tasks=[{
      id:1,
      name:"Task 1",
      day:"Monday",
    },
    {
      id:2,
      name:"Task 2",
      day:"Sunday",
    },]
  }
  
}
</script>


<style scoped>
.app{
  margin: auto;
  width:50vw;
  min-height:90vh;
  background-color: aliceblue;
  border-radius: 4px;
  padding: 20px;
  font-family: monospace;

}
::-webkit-scrollbar {
    width: 10px;
}
::-webkit-scrollbar-track {
    background: #92734a;
    border-radius: 4px;
}
::-webkit-scrollbar-thumb {
    background: #ffce94;
    border-radius: 4px;
}
</style>
