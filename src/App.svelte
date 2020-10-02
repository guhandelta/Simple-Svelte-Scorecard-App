<script>
	let name = "Aattakaaran";
	let points = 100;
	// const addPoint = () => (points += 1);
	const reducePoint = () => (points -= 1);
</script>

<style>
	h1 {
		color: purple;
	}
	h3 {
		margin-bottom: 10px;
		border-bottom: 2px solid #000;
	}
</style>
<div class="container">
	<div class="card">
		<h1>{name}</h1>
		<h3>{points}</h3>
		<button class="btn" on:click={() => (points += 1)}>Add Points</button>
		<button class="btn btn-dark" on:click={reducePoint}>Reduce Points</button>
	</div>
</div>