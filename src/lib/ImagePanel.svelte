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

<style>
    .panel {
        transform: rotateX(0deg);
        transition: 0.5s;
    }
    .panel:hover, .panel:active {
        transform: perspective(600px) rotateX(-10deg);
    }
    h2 {
        background-color: #2d39a9;
        transition: 0.5s;
    }
    .panel:hover h2, .panel:active h2 {
        background: #3C4DF2;
    }
</style>