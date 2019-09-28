<svelte:options immutable={true}/>

<script>
  import { slide } from "svelte/transition";
  export let operations = [];
</script>

<style>
    .history-list{
        position: absolute;
        right: 5%;
        top: 15%;
        height: 50%;
        overflow-y: auto;
        width: 250px;
    }

     button{
        padding: 15px;
        float: right;
        width: 150px;
        font-size: 25px;
        font-weight: 700;
        color: white;
        background-color: darkslateblue;
    }
</style>

<div class="history-list">
  {#if operations}
    {#each operations as operation}
      <div transition:slide>{operation}</div>
    {/each}
  {/if}
</div>
<button on:click>CLEAR</button>
