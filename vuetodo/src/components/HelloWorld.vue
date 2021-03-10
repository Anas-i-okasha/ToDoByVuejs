<template>
  <div >
    <h2> Todo list</h2>
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
    Addnew
  },
  data(){
    return {
      tasks:[

      ],
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
