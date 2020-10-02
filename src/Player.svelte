<script>
	export let name; //Instead of setting the values, get the values as/from the props
	export let points;
	// const addPoint = () => (points += 1);
	const reducePoint = () => (points -= 1);
	let showModifiers = false;
	const toggleModifiers = () => (showModifiers = !showModifiers);
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
<div class="card">
	<h1>
		{name}
		<button class="btn btn-sm" on:click={toggleModifiers}>
			{#if showModifiers}-{:else}+{/if}
		</button>
	</h1>
	<h3>Points: {points}</h3>
	{#if showModifiers}
		<button class="btn" on:click={() => (points += 1)}>Add Points</button>
		<button class="btn btn-dark" on:click={reducePoint}>Reduce Points</button>
		<input type="number" bind:value={points} />
	{/if}
</div>