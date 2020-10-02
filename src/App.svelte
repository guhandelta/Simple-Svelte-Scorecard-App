<script>
	import Navbar from './Navbar.svelte'
	import Player from './Player.svelte'

	const players = [
		{
			name: "Sachin Tendulkar",
			points: 90	
		},
		{
			name: "Mahinder Singh Dhoni",
			points: 97	
		},
		{
			name: "Virat Kholi",
			points: 88	
		},
	];
</script>

<Navbar />
<div class="container">
	{#if players.length === 0}
		<p>No Players Available</p>
	{:else}
		{#each players as player }
			<Player name={player.name} points={player.points} />
		{/each}
	{/if}
</div>