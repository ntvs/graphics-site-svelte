<script>
    import CoverPanel from '../lib/CoverPanel.svelte';
    import ImagePanel from '../lib/ImagePanel.svelte';
    import TextSection from '../lib/TextSection.svelte';

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


<TextSection options={{"heading":"About", "text":"NTVS is a 2D and 3D artist who specializes in making low-poly models, game assets, and avatars. He has been experimenting with digital art since 2012 using Adobe Photoshop. Over the years, he has integrated Blender into his workflow to establish a unique aesthetic which puts traditional 2D digital art into a new dimension.", "backgroundColor": "linear-gradient(rgb(196, 196, 196), rgb(108, 108, 108))", "headingColor": "rgb(242, 60, 60)", "textColor": "rgb(79, 13, 13)", "anchor": "about"}}/>


<style>
    .gridContainer {
        grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    }
    .gridContainer a {
        /*Safari experimental fix*/
        transform: translateZ(0);
    }
</style>