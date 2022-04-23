<script context="module">
	export async function load({ fetch, params }) {
		// console.log(params);
		const res = await fetch(
			`https://api.themoviedb.org/3/search/movie?api_key=dbceed12e440d492620b9f8d466bdc87&language=en-US&query=${params.id}&page=1`
		);
		const data = await res.json();
		console.log(data);
		if (res.ok) {
			return {
				props: { searchedMovie: data.results }
			};
		}
	}
</script>

<script>
	import MovieCard from '../../components/MovieCard.svelte';

	export let searchedMovie;
	console.log(searchedMovie);
</script>

<div class="searched-movies">
	{#each searchedMovie as movie}
		<MovieCard {movie} />
	{/each}
</div>

<style>
	.searched-movies {
		display: grid;
		grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
		grid-column-gap: 1rem;
		height: 20vh;
		grid-row-gap: 2rem;
	}
</style>
