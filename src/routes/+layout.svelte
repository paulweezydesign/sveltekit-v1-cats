<script>
  import "../app.postcss";
import Navbar from "../lib/Navbar.svelte";
import { fade, fly } from 'svelte/transition';
	let visible = true;
  import { onMount } from "svelte";
  import Header from "../lib/header/Header.svelte";
  import MoonSun from "../lib/MoonSun.svelte";
</script>


<Header />
<MoonSun />
  <main class="grid grid-cols-1 place-items-center h-screen container mx-auto">
    <slot />
  </main>



<style>
	:global(body) {
		background-color: #fff;
		color: #282828;
		transition: background-color 0.4s
	}
	:global(body.dark-mode) {
		background-color: #282828;
		color: #fff;
	}


</style>
