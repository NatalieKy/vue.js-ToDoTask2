<template>
  <div>
    <input type="text" v-model="task">
    <button @click="addTask">Add task</button>
  </div>
</template>

<script>
 export default {
   name: 'AddTodo',
   data() {
     return {
       task: ''
     }
   },
   methods: {
     addTask(){
       this.$emit('adder', this.task)
     }
   }
 }

</script>

<style>


</style>