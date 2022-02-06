<script>
    export let popular;
    import MovieCard from "./MovieCard.svelte"
    console.log(popular[0]);
</script>

<h3>Popular Movies</h3>
<div class="popular-movies">
    {#each popular as movie}
    <MovieCard {movie}/>
    {/each}
</div>