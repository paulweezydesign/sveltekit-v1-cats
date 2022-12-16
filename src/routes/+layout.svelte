<script>
  import "../app.postcss";
import Navbar from "../lib/Navbar.svelte";
import { fade, fly } from 'svelte/transition';
	let visible = true;
  import { onMount } from "svelte";
</script>


 <Navbar />

  <main class="grid grid-cols-1 place-items-center h-screen container mx-auto">
    <slot />
  </main>



<style>



</style>
