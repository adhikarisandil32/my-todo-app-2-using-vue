<template>
    <section>
        <h3>List of Todos: </h3>
        {{ todoLists }}
    </section>
</template>

<script setup>
    /* eslint-disable */
    defineProps({todoLists:Object}) //or defineProps(['todoLists'])
</script>

<style>

</style>