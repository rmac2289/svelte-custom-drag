<script>
	import { drag } from "./drag.js";
	import { fade } from "svelte/transition";
	let isVisible = true;
	function handleDragStop(e) {
		if (e.detail.x > 300) {
			isVisible = false;
		}
	}
</script>

<style>
	main {
		height: 100vh;
		display: flex;
		justify-content: center;
		align-items: center;
	}
	.box {
		width: 200px;
		height: 200px;
		background: blue;
	}
</style>

<main>
	<div class="box" transition:fade use:drag on:dragStop={handleDragStop} />
</main>
