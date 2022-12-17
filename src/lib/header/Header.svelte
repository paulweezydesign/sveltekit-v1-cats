<script>
    import {fly, fade} from 'svelte/transition'
  
    import AnimatedHamburger from '$lib/AnimatedHamburger.svelte'
    import logo from '$lib/images/svelte-logo.svg'
  
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
    <div class="flex justify-between">
      <div class="logo">
        <a href="https://kit.svelte.dev">
          <img src={logo} alt="SvelteKit" />
        </a>
      </div>
      <AnimatedHamburger {open} {onClick} />
    </div>
  
    {#if open}
    
      <nav
        class="absolute z-50 grid  w-full grid-cols-1   shadow-lg rouneded-md  place-items-center gap-2 bg-[#fff] pb-4"
        transition:fly={{y: -200, duration: 400}}
      >
        {#each links as { href, name }}
          <a class="decoration-secondary" {href}  on:click={() => open = !open}>{name}</a>
        {/each}
      </nav>
    {/if}
  </header>
  
  <style>
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
  