<script>
	let inputValue = '';
	let active = false;

	function cancelActive() {
		if (inputValue) {
			active = true;
		} else {
			active = false;
		}
	}
</script>

<form class="search">
	{#if !active}
		<label for="search_movie"> Search Movie</label>
	{/if}

	<input
		on:blur={cancelActive}
		on:focus={() => (active = true)}
		bind:value={inputValue}
		name="search_movie"
		type="text"
		class={active ? 'selected' : ''}
	/>
	{#if inputValue}
		<button>Search</button>
	{/if}
</form>

<style>
	.search {
		position: relative;
		width: 30%;
		margin: 1rem;
	}
	button {
		font-size: 0.7rem;
		padding: 0 1rem;
		background: rgb(96, 110, 201);
		color: white;
		font-weight: bold;
		border: none;
		height: 100%;
		border-top-right-radius: 10px;
		border-bottom-right-radius: 10px;
		cursor: pointer;
		position: absolute;
		bottom: 50%;
		right: 0;
		transform: translate(0, 50%);
	}
	input {
		width: 100%;
		border: none;
		font-size: 1rem;
		outline: none;
		color: rgb(255, 255, 255);
		padding: 0.5rem 1rem;
		font-weight: bold;
		background: rgb(63, 63, 63);
		border-radius: 10px;
		padding: 1rem;
		transition: background 0.75s ease-out;
	}

	label {
		position: absolute;
		font-size: 0.8rem;
		top: 50%;
		left: 0;
		pointer-events: none;
		color: white;
		padding: 0 1rem;
		transform: translate(0, -50%);
	}
	input.selected {
		background: black;
	}
</style>
