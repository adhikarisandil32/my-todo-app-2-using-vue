<template>
    <section>
        <!-- eslint-disable --> 
        <h3>List of Todos: </h3>
        <ul>
            <li v-for="(eachTodo, idx) in todoLists" :key="eachTodo.id">
                {{ eachTodo.title }}
                <!-- <button @click="removeClicked(todoLists, key)">Remove</button> -->
                <button @click="editClicked(idx)">Edit</button>
                <button @click="removeClicked(idx)">Remove</button>
            </li>
        </ul>
    </section>
</template>

<script setup>
    /* eslint-disable */
    
    //this is how we receive props directly into script
    const props = defineProps({todoLists:Object}) //or defineProps(['todoLists'])

    //function for button with event action removeClicked(key)
    let removeClicked = (removeFrom) => {
        props.todoLists.splice(removeFrom, 1)
    }

    let editClicked = (editFrom) => {
        const newInputText = prompt("Edit");
        if(newInputText.trim() === ""){
            return
        }
        props.todoLists[editFrom].title = newInputText;
    }
    //function for button with event action removeClicked(todoLists, key)
    /* let removeClicked = (todoLists, removeFrom) => {
        todoLists.splice(removeFrom, 1)
    } */
</script>

<style>

</style>