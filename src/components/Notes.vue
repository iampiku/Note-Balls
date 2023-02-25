<template>
  <TheCard
    variant="image"
    class="mx-auto w-full mb-3 sm:max-w-lg md:max-w-2xl lg:max-w-4xl"
  >
    <form @submit.prevent="$emit('noteSubmit', { note, createdAt })">
      <label
        for="message"
        class="block mb-2 text-sm font-medium text-gray-900 dark:text-white"
        >Your Note</label
      >
      <textarea
        id="message"
        rows="6"
        v-model="note"
        class="block p-2.5 w-full text-sm text-gray-900 bg-gray-50 rounded-lg border border-gray-300 focus:ring-blue-500 focus:border-blue-500 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500"
        placeholder="Add a new note here..."
      ></textarea>
      <div class="text-right">
        <Button class="my-2 px-6" :disabled="disableButton" size="sm">
          <template #prefix>
            <img src="../assets/addNotes.svg" alt="add" class="w-6" />
          </template>
          ADD
        </Button>
      </div>
    </form>
  </TheCard>
</template>

<script setup lang="ts">
import { Button, TheCard } from "flowbite-vue";
import { ref, computed } from "vue";

const note = ref<string>("");

const disableButton = computed((): boolean => {
  return note.value.length < 5;
});

const createdAt = computed((): string => {
  const date = new Date();
  return date.toLocaleDateString();
});
</script>
