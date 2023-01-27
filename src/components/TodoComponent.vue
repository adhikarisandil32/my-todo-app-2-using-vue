<template>
    <section>
        <h3>List of Todos: </h3>
        <ul>
            <li v-for="eachTodo in todoLists" :key="eachTodo.id">
                {{eachTodo.title}}
                <!-- <button @click="removeClicked(todoLists, key)">Remove</button> -->
                
                <button @click="removeClicked(key)">Remove</button>
            </li>
        </ul>
    </section>
</template>

<script setup>
    /* eslint-disable */

    const props = defineProps({todoLists:Object}) //or defineProps(['todoLists'])
    
    //function for button with event action removeClicked(key)
    let removeClicked = (removeFrom) => {
        props.todoLists.splice(removeFrom, 1)
    }

    //function for button with event action removeClicked(todoLists, key)
    /* let removeClicked = (todoLists, removeFrom) => {
        todoLists.splice(removeFrom, 1)
    } */
</script>

<style>

</style>