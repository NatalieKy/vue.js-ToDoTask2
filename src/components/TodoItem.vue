<template>
  <div>
    <h5>Todo Item</h5>
    <p>{{n}}. {{toDo}}</p>
    <span>
      <button @click="deleting">Delete toDo</button>
    </span>
  </div>
</template>

<script>
 export default {
   name: 'TodoItem',
   props: ['toDo', 'n'],
   methods: {
     deleting(){
       this.$emit('deleter', this.toDo)
     }
   }
 }

</script>

<style>


</style>