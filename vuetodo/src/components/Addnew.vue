<template>
    <div style="margin-top:50px;" class="container">
        <div class="text-center">
            <input class="form-control" placeholder="Enter your task here..." v-model="title">
        <button class="btn btn-dark btn-block" :disabled="!title" @click="addtask()" > Add Task </button>
        <button class="btn btn-danger btn-block" v-if="tasks.length>2" @click="deleteAll()">Delete All</button>
        <ul style=" list-style:none;  margin-top:30px;" v-bind:key="task.id" v-for="(task , index) in tasks">
            <li>
            {{task}}    <div style="margin-top:10px;"><button class="btn btn-danger" @click="deletetask(index)"> Delete the Task </button></div>  
            </li>
        </ul>
        </div>
        
    </div>
</template>

<script>
export default {
    name:"Addnew",
    props:['tasks'],
 data(){
     return {
         title:"",
         check:false
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