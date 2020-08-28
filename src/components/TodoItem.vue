<template>
  <div>
    <h5>Todo Item</h5>
    <span :class="{green: completed}">{{n}}.{{toDo}}</span>
    <hr>
    <span>
      <button @click="deleting">Delete task</button>
      <button @click="changer">change title</button>
      <button @click="completer">Complete task</button>
    </span>
    <hr>
  </div>
</template>

<script>
import {EventBus} from "@/main";
export default {
   name: 'TodoItem',
   props: ['toDo', 'n'],
   data() {
     return {
       title: 'oops!',
       completed: false
     }
   },
   methods: {
     deleting(){
       this.$emit('deleter', this.toDo)
     },
     completer(){
       this.completed = true

     },
     changer(){
       EventBus.$emit('changerOfButton', this.title)
     }
   },
}

</script>

<style>
.red{
  background: red;
}
.green{
  background: green;
}
</style>