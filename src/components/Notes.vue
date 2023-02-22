<template>
   <form>
      <label for="message" class="block mb-2 text-sm font-medium text-gray-900 dark:text-white">Your Note</label>
      <textarea id="message" rows="6" v-model="note" 
         class="block p-2.5 w-full text-sm text-gray-900 bg-gray-50 rounded-lg border border-gray-300 focus:ring-blue-500 focus:border-blue-500 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500"
         placeholder="Add a new note here..."></textarea>
      <Button class="my-2 bg-[#4D455D]" size="lg">ADD</Button>
   </form>
</template>

<script setup lang="ts">
import { Button } from 'flowbite-vue';
import { ref } from "vue";

const note = ref<string>('');
</script>
