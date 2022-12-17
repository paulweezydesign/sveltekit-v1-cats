<script>
    import Header from './header/Header.svelte';
    import logo from '../lib/images/svelte-logo.svg'
</script>


<nav class="grid grid-cols-2 md:grid-cols-4 items-center text-xl px-[7%] py-5">
    <div class="flex ">
      <img class="w-8" src={logo} alt='svelte logo' />
      <span class='mr-1'/>
      <a class="text-2xl lg:text-3xl font-black" href="/">SvelteKit app</a>
    </div>
    <div class="hidden md:col-span-2 md:flex md:justify-evenly">
      <a href="/about">About</a>
       <a href="/kittens">Kittens</a>
       <a href="/resources">Resources</a>
    </div>
    <div class="hidden md:flex md:justify-end">
      <a href="/contact">Contact us</a>
    </div>
    <div class='flex justify-end md:hidden'>
    <Header />
  </div>
  </nav>
