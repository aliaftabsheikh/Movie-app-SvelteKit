<script context="module">
	export async function load({ fetch }) {
		const res = await fetch(`
https://api.themoviedb.org/3/movie/popular?api_key=${import.meta.env.VITE_API}&language=en-US&page=1`);

		const data = await res.json();
		if (res.ok) {
			return {
				props: { popular: data.results }
			};
		}
	}
</script>

<script>
    
	import PopularMovie from '../components/PopularMovie.svelte';
	import SearchMovies from '../components/SearchMovies.svelte';
	export let popular;
    import {fly} from 'svelte/transition'
	import global from '../global.css';
    import Nav from '../components/Nav.svelte';

</script>

<section in:fly={{ y: 50, duration: 500 }} out:fly={{ duration: 500 }}>
    <Nav/>
	<SearchMovies />
	<PopularMovie {popular} />
</section>
