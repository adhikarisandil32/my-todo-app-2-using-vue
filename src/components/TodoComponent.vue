<template>
    <section>
        <h3>List of Todos: </h3>
        <ul>
            <li v-for="eachTodo in todoLists" :key="eachTodo.id">
                {{eachTodo.title}}
                <button @click="removeClicked(todoLists, key)">Remove</button>
            </li>
        </ul>
    </section>
</template>

<script setup>
    /* eslint-disable */
    defineProps({todoLists:Object}) //or defineProps(['todoLists'])

    let removeClicked = (todoLists, removeFrom) => {
        todoLists.splice(removeFrom, 1)
    }
</script>

<style>

</style>