<script context="module">
	export async function load({ fetch }) {
		const res = await fetch(`
https://api.themoviedb.org/3/movie/popular?api_key=d5c35e51c81488b19da7c1f572507a3d&language=en-US&page=1`);

		const data = await res.json();
		console.log(data);
		if (res.ok) {
			return {
				props: { popular: data.results }
			};
		}
	}
</script>

<script>
    import PopularMovie from "../components/PopularMovie.svelte";
    export let popular;
    import global from '../global.css'
</script>

<section>
    <PopularMovie {popular}/>
</section>