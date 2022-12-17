<script>

    import cats from "../data.js";

</script>
{#each cats as { id, name, src, href }, i}
<img src={url} alt={name} />
<h1 class="text-5xl text-center font-black">{name}</h1>
{/each}