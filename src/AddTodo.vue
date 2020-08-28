<template>
  <div>
    <input type="text" v-model="task">
    <button @click="addTask" ref="button" v-if="arrayOfTodo.length <5">Add task</button>
  </div>
</template>

<script>
import {EventBus} from "@/main";
export default {
  name: 'AddTodo',
  data() {
    return {
      title: 'oops!'
    }
  },
  props: [
      'arrayOfTodo'
  ],
  methods: {
    addTask(){
      this.$emit('adder', this.task)
    }
  },
  created() {
    EventBus.$on('changerOfButton', value => {
      if (this.$refs.button.textContent === 'Add task'){
        this.$refs.button.textContent = value
      } else {
        this.$refs.button.textContent = 'Add task'
      }
    })
  }
}

</script>

<style>


</style>