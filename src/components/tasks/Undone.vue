<script setup>
import { ref, computed } from 'vue';

defineProps({
    todo_list: {
    type: Array
  }
})

</script>

<template>
     <div class="border p-4 bg-neutral rounded shadow-md text-primary mt-4">
        <h3 class="text-lg text-rubik font-bold border-b border-primary">On your checklist</h3>
        <ul>
            <li v-for="item in todo_list" :key="item.key"
                class="mt-4 border border-primary p-4 rounded-lg flex flex-row justify-between">
                <div>
                    {{ item.task }}
                </div>
                <div>
                    {{ item.time }}
                    <input type="checkbox" v-model="item.done" class="rounded-[50%] ml-2">
                </div>
            </li>
        </ul>
        </div>
</template>