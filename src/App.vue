<template>
  <section class="w-full dark:bg-slate-700 h-screen">
    <!-- Navbar -->
    <NavBar></NavBar>
    <Toast
      type="success"
      closable
      divide
      v-if="showToast"
      class="border-solid border-emerald-700 z-20"
    >
      Note added successfully.
    </Toast>

    <main class="grid grid-row-3">
      <div class="mb-24"></div>

      <!-- Add Notes -->
      <Notes @noteSubmit="handleNoteSubmit"></Notes>

      <!-- View Notes -->
      <ViewNotes :notes="notes" @noteAction="handleNoteAction"></ViewNotes>
    </main>
  </section>
</template>

<script setup lang="ts">
import NavBar from "./components/NavBar.vue";
import Notes from "./components/Notes.vue";
import ViewNotes from "./components/ViewNotes.vue";

import { Toast } from "flowbite-vue";

import { ref } from "vue";

interface Note {
  note: string;
  createdAt: Date;
}

interface Action {
  type: "edit" | "delete";
  index: number;
}

const notes = ref<Note[]>([]);
const showToast = ref<boolean>(false);

function handleNoteSubmit(newNote: { note: string; createdAt: Date }): void {
  notes.value.push(newNote);
  handleToast();
}

function handleToast(): void {
  showToast.value = true;

  setTimeout((): void => {
    showToast.value = false;
  }, 3000);
}

function handleNoteAction({ type, index }: Action): void {
  switch (type) {
    case "edit":
      break;
    case "delete":
      notes.value.splice(index, 1);

      break;
    default:
      console.error("Wrong action type");
  }
}
</script>
