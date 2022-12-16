<script>
    import KittenCard from "../../lib/KittenCard.svelte";
 import cats from './data.js'
  </script>
  
  <div class="grid grid-cols-1 place-items-center h-full mx-auto">
    <h1 class="text-5xl sm:text-6xl md:text-7xl my-10 mx-auto px-6 font-black text-cetner md:hidden ">Let the <span class="text-gradient">cuteness</span> begin...</h1>
  <h1 class="text-6xl md:text-7xl  font-black text-cetner hidden md:flex mb-10  md:mx-auto px-4">Let the <span class="text-gradient">cuteness</span> begin...</h1>
      </div>
      <div class="mx-auto ">
      
        <div class="grid  sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4  xl:grid-cols-5 gap-6 mx-auto ">
          {#each cats as { id, name, src, href }, i}
            <div class=''>
              <a href="/kittens/{href}">
                <div class="relative rounded-lg hover:border-4 hover:shadow-lg hover:shadow-[rgb(var(--accent))] hover:border-[rgb(var(--accent))] transition-all 300 w-[250px] overflow-hidden shadow-lg shadow-black/50">
                  <div class="absolute z-50 bottom-3 left-3">
                    <h1 class="text-3xl z-50 font-black text-center">{name}</h1>
                  </div>
                  <img class="rounded hover:scale-105  hover:border-4 hover:border-[rgb(var(--accent))] transition-all 300" {src} alt="pic of {name} the cat" />
                </div>
              </a>
            </div>
          {/each}
          </div>
  
        
      </div>

  
  <style>
    .grid-1 {
      grid-template-columns: 
    repeat(auto-fit, minmax(250px, 5fr));

    }
    :root {
		--accent: 124, 58, 237;
		--accent-gradient: linear-gradient(45deg, rgb(var(--accent)), #da62c4 30%, white 60%);
	}

	.text-gradient {
		background-image: var(--accent-gradient);
		-webkit-background-clip: text;
		-webkit-text-fill-color: transparent;
		background-size: 400%;
		background-position: 0%;
	}
  </style>