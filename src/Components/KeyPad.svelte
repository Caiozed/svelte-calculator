<script>
	import Button from './Button.svelte';
</script>

<style>
    table{
        margin:0 auto;
    }
</style>

<table>
    <tr>
        <tb><Button on:addnumber number="C"></Button></tb>
        <tb><Button on:addnumber number="DEL"></Button></tb>
        <tb><Button on:addnumber number="+"></Button></tb>
        <tb><Button on:addnumber number="-"></Button></tb>
    </tr>
    <tr>
        <tb><Button on:addnumber number=7></Button></tb>
        <tb><Button on:addnumber number=8></Button></tb>
        <tb><Button on:addnumber number=9></Button></tb>
        <tb><Button on:addnumber number="/"></Button></tb>
    </tr>
     <tr>
        <tb><Button on:addnumber number=4></Button></tb>
        <tb><Button on:addnumber number=5></Button></tb>
        <tb><Button on:addnumber number=6></Button></tb>
        <tb><Button on:addnumber number="*"></Button></tb>
    </tr>
     <tr>
        <tb><Button on:addnumber number=1></Button></tb>
        <tb><Button on:addnumber number=2></Button></tb>
        <tb><Button on:addnumber number=3></Button></tb>

    </tr>
     <tr>
        <tb ><Button on:addnumber number="."></Button></tb>
        <tb><Button on:addnumber number=0></Button></tb>
        <tb colspan="3"><Button on:addnumber number="="></Button></tb>
    </tr>
</table>
