<template>
    <div>
        <input placeholder="Enter your task here..." v-model="title">
        <button :disabled="!title" @click="addtask()" > Add Task </button>
        <button v-if="tasks.length>2" @click="deleteAll()">Delete All</button>
        <ul v-bind:key="task.id" v-for="(task , index) in tasks">
            <li>
          <input type="checkbox">   {{task}}  <button @click="deletetask(index)"> Delete the Task </button>
            </li>
        </ul>
    </div>
</template>

<script>
export default {
    name:"Addnew",
    props:['tasks'],
 data(){
     return {
         title:""
     }
 },
 methods:{
     addtask:function() {
         this.tasks.push(this.title);
         this.title="";
     },
     deletetask: function(index){
         this.tasks.splice(index , 1)
     },
     deleteAll: function(){
         this.tasks=[];
     }
 }
}
</script>