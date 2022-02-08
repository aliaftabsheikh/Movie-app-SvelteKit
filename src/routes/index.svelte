<script context="module">
	export async function load({ fetch }) {
		const res = await fetch(`
https://api.themoviedb.org/3/movie/popular?api_key=d5c35e51c81488b19da7c1f572507a3d&language=en-US&page=1`);

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
	export let popular;
	import SearchMovies from '../components/SearchMovies.svelte';
	import global from '../global.css';
    import {fly} from 'svelte/transition'

</script>

<section in:fly={{ y: 50, duration: 500 }} out:fly={{ duration: 500 }}>
	<SearchMovies />
	<PopularMovie {popular} />
</section>
