<script context="module">
	export async function load({ fetch }) {
		const res = await fetch(
			`https://api.themoviedb.org/3/discover/movie?api_key=dbceed12e440d492620b9f8d466bdc87&language=en-US`
		);
		const data = await res.json();

		if (res.ok) {
			return {
				props: { popular: data.results }
			};
		}
	}
</script>

<script>
	import PopularMovies from '../components/PopularMovies.svelte';
	import SearchMovies from '../components/SearchMovies.svelte';
	export let popular;
</script>

<section>
	<SearchMovies />
	<PopularMovies {popular} />
</section>

<!-- //dbceed12e440d492620b9f8d466bdc87 -->
<style>
	:global(*) {
		margin: 0;
		padding: 0;
		box-sizing: border-box;
	}
	:global(body) {
		margin: 0 10%;
	}
</style>
