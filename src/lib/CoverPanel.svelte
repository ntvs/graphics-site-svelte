<script>
    export let heading = "";
    export let image = "";
</script>

{#if image}
    <div class="cover" style="background-image: url('{image}');">
        <div class="container">
            <h1>{heading}</h1>
        </div>
    </div>
{/if}

<style>
    .cover .container h1 {
        color: white;
        padding: 0 0 4vh 3vw;
        font-size: max(2.8em, 5vw);
    }
</style>