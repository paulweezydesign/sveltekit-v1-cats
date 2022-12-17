<script>
	import { theme } from './../../stores/theme.ts';
    import {fly, fade} from 'svelte/transition'
  import MoonSun from '../MoonSun.svelte';
    import AnimatedHamburger from '$lib/AnimatedHamburger.svelte'
    import logo from '$lib/images/svelte-logo.svg'
    import Button from '../Button.svelte';
    export let open = false
    export let onClick = () => {
      open = !open
    }
  
    let links = [
      {href: '/', name: 'Home'},
      {href: '/about', name: 'About'},
      {href: '/kittens', name: 'Kittens'},
      {href: '/resources', name: 'Resources'},
      {href: '/contact', name: 'Contact'},
    ]
  </script>
  
  <header class="text-primary">
    <div class="grid grid-cols-2 md:grid-cols-4 items-center px-[7%] text-xl py-4 ">
      <div class="logo flex flex-row">
        <a href="/">
          <img src={logo} alt="SvelteKit" /> 
          <h1 class="hidden md:flex sm:text-2xl  font-black">SvelteKite App</h1>
        </a>
      </div>
      <div class="hidden md:flex md:col-span-2 md:justify-evenly">
        <a href="/about">About</a>
        <a href="/kittens">Kittens</a>
        <a href="/resources">Resources</a>
      </div>
      <div class="hidden md:flex md:justify-end">
        <Button>
        Toggle
        </Button>
        <a class="btn bg-purple-700 rounded " href="/contact">Contact us</a>
      </div>
      <div class="flex justify-end md:hidden">
      <AnimatedHamburger {open} {onClick} />
    </div>
    </div>
  
    {#if open}

      <nav
        class="absolute z-[1300] grid h-[400px] w-full grid-cols-1   shadow-lg rouneded-md place-items-center gap-2 bg-[#fff] pb-4"
        transition:fly={{y: -200, duration: 400}}
      >
        {#each links as { href, name }}
          <a class="decoration-secondary" {href}  on:click={() => open = !open}>{name}</a>
        {/each}
      </nav>
    {/if}
  </header>
  
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
    header {
      position: relative;
      font-size: 2rem;
      z-index: 2;
    }
  
    .logo {
      width: 3em;
      height: 3em;
    }
  
    .logo a {
      display: flex;
      align-items: center;
      justify-content: center;
      width: 100%;
      height: 100%;
    }
  
    .logo img {
      width: 2em;
      height: 2em;
      object-fit: contain;
    }
  </style>
  