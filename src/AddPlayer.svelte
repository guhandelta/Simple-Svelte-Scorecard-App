<script>
    import { createEventDispatcher } from 'svelte';
    
    const dispatch = createEventDispatcher();

    let player = {
        name: "",
        points: 0
    };
    const submitForm = e => {
        e.preventDefault();
        dispatch("addplayer",player); //Dispatch an event, addplayer, with the player data from the form
        // Clear the form
        player = {
            name: "",
            points: 0
        };
    }
</script>

<form on:submit={submitForm} class="grid-3">
    <input type="text" placeholder="Player Name" bind:value={player.name}>
    <input type="number" placeholder="Player Score" bind:value={player.points}>
    <input type="submit" class="btn btn-primary" value="Add Player">
</form>