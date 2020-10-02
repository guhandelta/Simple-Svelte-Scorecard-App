<script>
	import {createEventDispatcher} from 'svelte'

	const dispatch = createEventDispatcher();

	export let name; //Instead of setting the values, get the values as/from the props
	export let points;
	let showModifiers = false;

	// const addPoint = () => (points += 1);
	const reducePoint = () => (points -= 1);
	const toggleModifiers = () => (showModifiers = !showModifiers);
	const onDelete = () => dispatch("removeplayer", name); //a unique ID or data should be passed-
	//- but for this case the player name is used here as a unique identifyer
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
		<button class="btn btn-danger btn-sm" on:click={onDelete}>x</button>
	</h1>
	<h3>Points: {points}</h3>
	{#if showModifiers}
		<button class="btn" on:click={() => (points += 1)}>Add Points</button>
		<button class="btn btn-dark" on:click={reducePoint}>Reduce Points</button>
		<input type="number" bind:value={points} />
	{/if}
</div>