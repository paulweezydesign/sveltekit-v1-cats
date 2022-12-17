<script>
import Modal from "../lib/modal/Modal.svelte";

</script>

<svelte:head>
	<title>Home</title>
	<meta name="description" content="Svelte demo app" />
</svelte:head>

<section class="grid grid-cols-1 place-items-center h-screen px-6">
	<main class="">
	  <div class="">
		<h1 class="text-6xl md:text-7xl lg:text-8xl font-black">
		  Come adopt my cute
		  <br class="hidden md:block" /> ass kittens.
		</h1>
		<p class="text-xl prose lg:prose-2xl">
		  They deserve a good home with plenty of love and affection, annd
		  snacks aaannnndddd belly rubbs!
		</p>
		<button class=" px-8 py-3 text-lg rounded border-2 bg-inherit border-[#282828 dark:bg-[#fff] dark:text-[#282828] text-[#fff]">Click here</button>
		<div class="">
		  <a class="btn rounded border-2 border-[#242424] bg-[#282828] dark:bg-[#fff]" href="/about">
			Learn more
		  </a>
		  <a
			class="btn rounded hover:shadow-lg hover:shadow-[deepink]/30 transition-all bg-[deeppink] border-[deeppink] border-2 hover:bg-[hotpink] hover:border-[hotpink] hover:text-white"
			href="/kittens"
		  >
			To Cuteness
		</a>
		</div>
	  </div>
	</main>
  </section> 

<style>
				:global(body) {
		background: #fff;
		color: #282828;
		transition: background-color 0.4s
	}
	:global(body.dark-mode) {
		background: #282828;
		color: #fff;
		
	}
		:root {
		--accent: 124, 58, 237;
		--accent-gradient: linear-gradient(45deg, rgb(var(--accent)), #da62c4 30%, white 60%);
			--dark-inverse: @apply bg-[#fff];
			--light-inverse: @apply bg-[]
	}

	.text-gradient {
		background-image: var(--accent-gradient);
		-webkit-background-clip: text;
		-webkit-text-fill-color: transparent;
		background-size: 400%;
		background-position: 0%;
	}
</style>
