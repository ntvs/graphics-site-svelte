<script>
    import { fade } from "svelte/transition";
    //import ImageModal from '../../lib/ImageModal.svelte';
    import TextPanel from '../../lib/TextPanel.svelte';

    let projects = [
        {"image": "https://i.imgur.com/dpKPj6l.png", "name": "Low Poly ISS Cupola", "tags": ["3D Model"]},
        {"image": "https://i.imgur.com/LRgHbFH.gif", "name": "Low Poly Canadarm2", "tags": ["3D Model"]},
        {"image": "https://i.imgur.com/2xVjJKO.png", "name": "Low Poly Ferrari SF90", "tags": ["3D Model"]},
        {"image": "https://i.imgur.com/o9ulwJB.png", "name": "Low Poly Stock Car Asset", "tags": ["3D Model"]},
        {"image": "https://i.imgur.com/ZfVTIDy.png", "name": "2022 WAS Power Ranking", "tags": ["Digital Art"]},
        {"image": "https://i.imgur.com/tD7CESp.png", "name": "Melee At The Elm Top 8", "tags": ["Digital Art"]},
        {"image": "https://i.imgur.com/aikFR8B.png", "name": "Melee At The Elm Top 3", "tags": ["Digital Art"]},
        {"image": "https://i.imgur.com/miAV3pJ.png", "name": "Melee Monthly Custom Font & Logo", "tags": ["Logo"]},
        {"image": "https://i.imgur.com/Grm9L3A.png", "name": "Dallasmed65 Avatar", "tags": ["Digital Art"]},
        {"image": "https://i.imgur.com/We9oyuK.png", "name": "AdzyMCPE Avatar", "tags": ["Digital Art"]},
        {"image": "https://i.imgur.com/7pZy6Qx.png", "name": "Cmrowlee Avatar", "tags": ["Digital Art"]},
        {"image": "https://i.imgur.com/e6dNcdt.png", "name": "Dog Avatar", "tags": ["Digital Art"]},
        {"image": "https://i.imgur.com/QYRgakv.png", "name": "Spriyo Avatar", "tags": ["Digital Art"]},
        {"image": "https://i.imgur.com/GtUr6KW.png", "name": "Bowldar Avatar", "tags": ["Digital Art"]},
        {"image": "https://i.imgur.com/RvT1C2f.png", "name": "itspeepachu Avatar", "tags": ["Digital Art"]},
        {"image": "https://i.imgur.com/RPbx41S.png", "name": "Desiiiqner Avatar", "tags": ["Digital Art"]},
        {"image": "https://i.imgur.com/UzuCc7a.png", "name": "Veloxic Avatar", "tags": ["Digital Art"]},
        {"image": "https://i.imgur.com/GKjYDyk.png", "name": "FuzzyWuzzyDucky Avatar", "tags": ["Digital Art"]},
        {"image": "https://i.imgur.com/CWy780F.png", "name": "Rigged 2.5D Character", "tags": ["Digital Art", "Sprite"]},
        {"image": "https://i.imgur.com/Dj9mVv0.png", "name": "Character Spritesheet", "tags": ["Digital Art", "Sprite"]},
        {"image": "https://i.imgur.com/TwWusiG.png", "name": "Mock Game Scene", "tags": ["Digital Art", "Sprite"]},
        {"image": "https://i.imgur.com/4cO2ogr.png", "name": "Ocean Creature", "tags": ["Digital Art", "Sprite"]},
        {"image": "https://i.imgur.com/Pcsr2kA.jpg", "name": "The Originals Cover", "tags": ["Digital Art"]},
        {"image": "https://i.imgur.com/FEvhlAZ.png", "name": "3D Bust", "tags": ["Digital Art", "3D Model"]},
        {"image": "https://i.imgur.com/vpN6EAE.png", "name": "Character Select Screen Concept", "tags": ["Concept Art"]},
        {"image": "https://i.imgur.com/AxQOap9.png", "name": "Personal Logos", "tags": ["Logo"]}

    ];
    
    //Modal state
    let modalOpen = false;
    let selectedProject = {"image":"", "alt":""};

    //$: console.log(modalOpen);

    let toggleModal = () => {modalOpen = !modalOpen};
    let updateModal = (image, alt) => {
        selectedProject = {image, alt}
    };
</script>

<svelte:head>
    <title>Work | NTVS</title>
</svelte:head>

<div class="container" style="padding: 1em 0">

    <!--Display each project as an image with tags-->
    <div class="gridContainer">
        {#each projects as project}
            <TextPanel object={project} on:click={() => {toggleModal(); updateModal(project.image, "");}} on:keypress={() => {toggleModal(); updateModal(project.image, "");}} />
        {/each}
    </div>

    <!--Modal component test code - lags-->
    <!-- <span class:invisible={!modalOpen} style="transition: 1s;">
        <ImageModal image={selectedProject.image} alt={selectedProject.alt} on:close={toggleModal}/>
    </span> -->

    {#if modalOpen}
        <div class="modal" transition:fade on:click={() => {modalOpen = false}} on:keypress={() => {modalOpen = false}}>
            <div class="container">
                <img src="{selectedProject.image}" alt="{selectedProject.alt}">
            </div>
        </div>
    {/if}

</div>

<style>

    .modal img {
        max-width: 100%;
        max-height: 80vh;
    }

    .gridContainer {
        grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
    }

</style>