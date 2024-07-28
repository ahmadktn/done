<script setup>
    import { ref, computed } from 'vue';
    import Done from './tasks/Done.vue';
    import Undone from './tasks/Undone.vue';
    import AddNew from './AddNew.vue';

    const todo_list = ref([
        
    ])

    const filterUndone = computed(() => {
        return todo_list.value.filter(item => item.done == false)
    });

    const filterDone = computed(() => {
        return todo_list.value.filter(item => item.done == true)
    });

    const addTodo = (new_task, new_task_time) => {
        todo_list.value.push({
            task: new_task,
            done: false,
            key: todo_list.value.length + 1,
            time: new_task_time,
        });
    }
</script>

<template>
    <main class="w-full">
        <AddNew @addTodo="addTodo"/>

        <Undone :todo_list="filterUndone"/>

        <Done :todo_list="filterDone"/>
    </main>
</template>