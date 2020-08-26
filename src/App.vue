<template>
  <div >
    <h1>Task application</h1>
    <AddTodo @adder="adder"/>
    <TodoList
        :arrayOfTodo="arrayOfTodo"
        @deletter="splicer"
    />
  </div>
</template>


<script>
  import AddTodo from "@/AddTodo";
  import TodoList from "@/TodoList";

  export default {
    name: 'App',
    components: {
      AddTodo,
      TodoList
    },
    data() {
      return {
        arrayOfTodo: ['wake up', 'clean teeth']
      }
    },
    methods: {
      adder(event) {
        this.arrayOfTodo.push(event)
      },
      splicer(){
        this.arrayOfTodo.splice(this.toDo, 1)
      }
    }
  }

</script>

<styles>


</styles>