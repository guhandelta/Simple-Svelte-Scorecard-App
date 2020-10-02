<script>
	import Navbar from './Navbar.svelte'
	import Player from './Player.svelte'
	import AddPlayer from './AddPlayer.svelte'

	let players = [
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

	// Since the Player and AddPlayer are below App, the events dispatched will reach this component-
	//- by event bubbling 
	const addPlayer = e => {
		const newPlayer = e.detail; // get the value passed is through e.detail
		// Pushing the new player values into the array won't be reactive, can accomplish the same using-
		//- .concat() or using ... 
		players = [...players, newPlayer];
	};
	const removePlayer = e =>{
		players = players.filter(player => player.name !== e.detail);
	};
</script>

<Navbar />
<div class="container">
	<AddPlayer on:addplayer={addPlayer} />
	{#if players.length === 0}
		<p>No Players Available</p>
	{:else}
		{#each players as player }
			<Player name={player.name} points={player.points} on:removeplayer={removePlayer} />
		{/each}
	{/if}
</div>