<script>
	import { clickOutside } from "../click_outside.js";

	let showModal = false;
</script>

<button on:click={() => (showModal = true)}>Show Modal</button>
{#if showModal}
	<div class="box" use:clickOutside on:outclick={() => (showModal = false)}>
		<div class="flex justify-end">
		<button class="text-3xl" on:click={() => (showModal = false)}>X</button>
	</div>
		Click outside me!
	</div>
{/if}

<style>
	.box {
		--width: 100vw;
		--height: 100vh;
		position: absolute;
		width: var(--width);
		height: var(--height);
		left: calc(50% - var(--width) / 2);
		top: calc(50% - var(--height) / 2);
		
		padding: 8px;
		border-radius: 4px;
		background-color: #ff3e00;
		color: #fff;
		text-align: center;
		font-weight: bold;
	}
</style>
