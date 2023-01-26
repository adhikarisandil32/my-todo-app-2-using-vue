<template>
  <main>
    <form @submit.prevent="addNewTodo">
      Add a todo:
      <input type="text" placeholder="e.g. make a video" >
      <button>Add</button>
    </form>
    <TodoComponent :x.prop="todos"/>
  </main>
</template>

<script setup>
/*eslint-disable*/

import TodoComponent from './components/TodoComponent.vue'
import {ref} from 'vue'

const todos = ref([{name:"John"}])
const newTodo = ref('')

/* function addNewTodo(){
  todos.value.push({
    title: newTodo
  })
} */

</script>



<style scoped>
  main{
    width: 600px;
    margin: 0 auto;
  }
</style>
