<style>
    input{
        padding: 5px;
        border: 2px solid grey;
        font-size: 30px;
        display: block;
        margin: 0 auto;
        text-align: right;
        width: 100%;
    }
</style>

<script>
    export let result = 0;
    export let lastNumber = 0;
</script>

<input type="text" bind:value={result}>