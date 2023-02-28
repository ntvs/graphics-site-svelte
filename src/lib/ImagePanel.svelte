<script>
    export let title = "Title";
    export let image = "";
    export let alt = "Image description";
</script>

<div class="panel">
    {#if title}
        <h2>{title}</h2>
    {/if}
    <img src="{image}" alt="{alt}">
</div>