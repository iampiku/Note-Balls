<template>
  <!-- Notes -->
  <template v-if="notes.length">
    <TheCard
      class="mx-auto mb-2 w-full sm:max-w-lg md:max-w-2xl lg:max-w-4xl"
      v-for="({ note, createdAt }, index) in notes"
      :key="index"
    >
      <p>
        {{ note }}
      </p>
      <p class="text-right">{{ createdAt }}</p>

      <!-- Card Action -->
      <div class="flex justify-between my-2">
        <Button
          size="sm"
          class="px-10"
          @click="$emit('noteAction', { type: 'edit', index })"
        >
          <template #prefix>
            <img src="../assets/editNotes.svg" alt="edit" class="w-6" />
          </template>
          EDIT
        </Button>
        <Button
          size="sm"
          class="px-10"
          @click="$emit('noteAction', { type: 'delete', index })"
        >
          <template #prefix>
            <img src="../assets/deleteNotes.svg" alt="delete" class="w-6" />
          </template>
          DELETE
        </Button>
      </div>
    </TheCard>
  </template>
</template>

<script setup lang="ts">
import { Button, TheCard } from "flowbite-vue";

interface Note {
  note: string;
  createdAt: Date;
}

defineProps<{
  notes: Note[];
}>();
</script>
