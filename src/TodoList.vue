<template>
  <div>
    <h3>Todo list</h3>
    <p v-for="(toDo, n) in arrayOfTodo" :key="n">
      <TodoItem
          :toDo="toDo"
          :n="n"
          @deleter="deleter"
      />
    </p>
  </div>
</template>

<script>
  import TodoItem from "@/components/TodoItem";
  export default {
    name: 'TodoList',
    components: {
      TodoItem
    },
    props: ['arrayOfTodo'],
    methods: {
      deleter(toDo){
        this.$emit('deletter', toDo)
      }
    }
  }

</script>

<style>


</style>