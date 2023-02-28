<script>
    import CoverPanel from '../lib/CoverPanel.svelte';
    import ImagePanel from '../lib/ImagePanel.svelte';

    let featured = [
        {"title": "Digital Art", "image": "https://i.imgur.com/hpDVO2w.png", "alt": "Digital Art"},
        {"title": "Visualizations", "image": "https://i.imgur.com/CNmMpIm.png", "alt": "Visualizations"},
        {"title": "Game Assets", "image": "https://i.imgur.com/6Uqhv5Z.gif", "alt": "Game Assets"},
    ];
</script>

<svelte:head>
    <title>Home | NTVS</title>
</svelte:head>

<CoverPanel heading="Digital art, visualizations and game assets." image="https://i.imgur.com/LRgHbFH.gif"/>

<div class="container" style="padding: 1em 0">
    <div class="gridContainer">
        {#each featured as panel}
            <a href="/work"><ImagePanel title="{panel.title}" image="{panel.image}" alt="{panel.alt}"/></a>
        {/each}
    </div>
</div>

<style>
    .gridContainer {
        grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    }
</style>