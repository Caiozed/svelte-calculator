<script>
    import {createEventDispatcher } from 'svelte';
    export let number;
	const dispatch = createEventDispatcher();

    function addNumber() {
		dispatch('addnumber', {
			number: number
		});
	}
</script>

<style>
    button{
        padding: 15px;
        width: 100px;
        font-size: 25px;
        font-weight: 700;
        color: white;
        background-color: darkslateblue;
    }
</style>

<button on:click={addNumber}>{number}</button>