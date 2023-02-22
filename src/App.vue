<template>
	<section class="grid grid-rows-3">
		<nav>
			<NavBar></NavBar>
		</nav>
		<main class="row-span-3">
			<div class="p-8 md:mx-52 sm:mx-24 bg-[#E96479] rounded-lg">
				<Notes></Notes>
			</div>
		</main>
	</section>
</template>

<script setup lang="ts">
import NavBar from './components/NavBar.vue';
import Notes from './components/Notes.vue';
</script>
