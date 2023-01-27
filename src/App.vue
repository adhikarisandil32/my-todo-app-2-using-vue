<template>
  <main>
    <form @submit.prevent="addNewTodo">
      Add a todo:
      <input type="text" placeholder="e.g. make a video" v-model="newTodo">
      <button>Add</button>
    </form>
    <TodoComponent :todoLists="todos"/> <!-- todos passed as props -->
  </main>
</template>

<script setup>
/*eslint-disable*/

import TodoComponent from './components/TodoComponent.vue'
import {ref} from 'vue'

//boilerplate todos. its is the list of todos with id and title
//this is where after click event, the id and title of todo is pushed
const todos = ref([])
let newTodoId = ref(0)

const newTodo = ref('') //newTodos, specially titles

function addNewTodo(){
  if(newTodo.value.trim() === ""){
    return
  }
  todos.value.push({
    id: newTodoId.value++,
    title: newTodo.value
  })
  newTodo.value = '';
}

</script>

<style scoped>
  main{
    width: 600px;
    height: 100vh;
    margin: 0 auto;
    padding: 12px 24px 0 24px;
    background-color: rgb(222, 236, 249);
  }
</style>
