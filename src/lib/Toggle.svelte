<script>
	import { fly } from './transitions.js';
	
	let open = false;
</script>
<svelte:head>

</svelte:head>
<button class='text-xl' on:click={() => open = !open}>Toggle</button>

{#if open}
Hello
{/if}

<style>
	
</style>