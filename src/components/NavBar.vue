<template>
  <Navbar :sticky="true">
    <template #logo>
      <div class="flex">
        <img src="../assets/note-2-svgrepo-com.svg" alt="Notes" />
        <span class="text-slate-800 p-3 font-medium dark:text-slate-300"
          >Note Balls</span
        >
      </div>
    </template>

    <template #default="{ isShowMenu }">
      <NavbarCollapse :is-show-menu="isShowMenu">
        <NavbarLink>Notes</NavbarLink>
        <NavbarLink>Stats</NavbarLink>
      </NavbarCollapse>
    </template>
  </Navbar>
</template>

<script setup lang="ts">
import { Navbar, NavbarCollapse, NavbarLink } from "flowbite-vue";
</script>
