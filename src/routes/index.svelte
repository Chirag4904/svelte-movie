<script context="module">
	export async function load({ fetch }) {
		const res = await fetch(
			`https://api.themoviedb.org/3/discover/movie?api_key=dbceed12e440d492620b9f8d466bdc87&language=en-US`
		);
		const data = await res.json();
		console.log(res);
		if (res.ok) {
			return {
				props: { popular: data.results }
			};
		}
	}
</script>

<!-- //dbceed12e440d492620b9f8d466bdc87 -->
