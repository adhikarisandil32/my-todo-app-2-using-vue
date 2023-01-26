<template>
  <main>
    <form @submit.prevent="addNewTodo">
      Add a todo:
      <input type="text" placeholder="e.g. make a video" >
      <button>Add</button>
    </form>
    <TodoComponent :todoLists="todos"/>
  </main>
</template>

<script setup>
/*eslint-disable*/

import TodoComponent from './components/TodoComponent.vue'
import {ref} from 'vue'


const todos = ref([
  {
    id:"1",
    title:"make a video"
  },
  {
    id:"2",
    title:"edit the video"
  },
  {
    id: "3",
    title: "create a youtube channel"
  }
])
const newTodo = ref('')
const newId = 4

function addNewTodo(){
  todos.value.push({
    id: newId++,
    title: newTodo
  })
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
