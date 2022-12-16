<script>
	import { fly } from './transitions';
	import { clickOutside } from "./click_outside.js";
	let open = false;
</script>
<svelte:head>

</svelte:head>
<button class='' on:click={() => open = !open} >
	<i class="fa-solid fa-bars text-4xl"></i>
</button>

{#if open}
<div class="bg-black/40 contrast fixed inset-0" />
  <div class="fixed top-0 right-0 h-screen w-[350px] bg-white z-[100] shadow-lg" transition:fly={{ x: '100%' }} use:clickOutside on:outclick={() => open = !open}>
<div class="flex justify-star mt-6 ml-4">
	<button class='close close:hover text-4xl' on:click={() => open = !open}>&times;</button>
</div>	
<section class="grid grid-cols-1 place-items-center h-screen">
	<div class="flex flex-col justify-evenly h-1/2">
		<a href="/" on:click={() => open = !open}>Home</a>
		<a href="/about" on:click={() => open = !open}>About</a>
		<a href="/kittens" on:click={() => open = !open}>Kittens</a>
		<a href="/resources" on:click={() => open = !open}>Resources</a>
		<a href="/contact" on:click={() => open = !open}>Contact</a>
	</div>
</section>
</div>
{/if}

<style>
	.contrast {
  backdrop-filter: contrast(2);  
}
	.close {
		background: transparent;
		border: none;
	
	}
	.drawer {
		position: fixed;
		z-index: 200;
		top: 0;
		right: 0;
		background: #ddd;
		padding: 16px;
		height: 100vh;
		width: 350px;
		background: white;
		border-left: 1px solid rgba(0, 0, 0, .1);
		box-shadow: -2px 0px 6px -1px rgba(0, 0, 0, 0.1);
	}
	.close:hover {
		color: red;
		scale: 108%;
		transition: all;
		easing: ease-out;
	}
</style>