<template>
  <div style="margin-top:50px;" class="container">
    <h2 class="text-center"> Todo list</h2>
    <div>
      <Addnew v-bind:tasks="tasks"/>
    </div>
  </div>
</template>

<script>
import Addnew from './Addnew'
export default {
  name: 'HelloWorld',
  components:{
    Addnew,
  },
  data(){
    return {
      tasks:[

      ],
    }
  }
}
</script>

