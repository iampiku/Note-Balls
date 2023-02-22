<template>
   <Navbar :sticky="true" class="bg-[#7DB9B6]">
      <template #logo>
         <div class="flex">
            <img src="../assets/note-2-svgrepo-com.svg" alt="Notes">
            <span class="text-slate-800 p-3 font-medium">Note Balls</span>
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
import { Navbar, NavbarCollapse, NavbarLink } from 'flowbite-vue';
</script>