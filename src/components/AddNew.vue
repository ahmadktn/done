<script setup>
import { ref } from 'vue';

const new_task = ref('');
const new_task_time = ref('');

</script>

<template>
    <div class="flex flex-col items-center w-full">
        <div class="flex flex-col sm:flex-row gap-2 w-full">
            <input type="text" v-model="new_task"
                placeholder="What's on your mind?"
                class="border bg-neutral w-full p-3 rounded border-secondary border-2 text-primary outline-none">
            <input type="time" v-model="new_task_time"
                class="border bg-neutral w-1/2 p-3 rounded border-secondary border-2 text-primary outline-none">
        </div>
        
        <input type="submit" value="Add Task" 
            class="w-full p-3 mt-4 cursor-pointer shadow-lg rounded bg-secondary text-neautral text-rubik outline-none font-bold"
            @click="$emit('addTodo', new_task, new_task_time); new_task=''; new_task_time='';">
    </div>
</template>