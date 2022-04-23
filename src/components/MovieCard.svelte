<script>
	export let movie;
</script>

<div class="movie-card">
	<a href={'/movie/' + movie.id}>
		<img src={'https://image.tmdb.org/t/p/w500' + movie.poster_path} alt={movie.title} />
	</a>
	<div class="description">
		<h2>{movie.title}</h2>
		<p>{movie.release_date}</p>
	</div>
</div>

<style>
	.movie-card {
		/* margin-bottom: 0.5rem; */
		display: flex;
		flex-direction: column;
		justify-content: space-around;
		padding: 1rem;
	}
	img {
		width: 90%;
		height: 30vh;
		object-fit: cover;
		border-radius: 1rem;
		margin-bottom: 0.5rem;
	}
	h2 {
		font-size: 1rem;
		margin-bottom: 0.5rem;
	}
	.description {
		height: 6vh;
	}
	p {
		font-size: 0.9rem;
	}
</style>
