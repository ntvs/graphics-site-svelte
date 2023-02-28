<script>
    import { fade } from "svelte/transition";
    import ImageModal from '../../lib/ImageModal.svelte';

    let projects = [
        {"image": "https://i.imgur.com/dpKPj6l.png", "name": "Low Poly ISS Cupola", "tags": ["3D Model"]},
        {"image": "https://i.imgur.com/LRgHbFH.gif", "name": "Low Poly Canadarm2", "tags": ["3D Model"]},
        {"image": "https://i.imgur.com/2xVjJKO.png", "name": "Low Poly Ferrari SF90", "tags": ["3D Model"]},
        {"image": "https://i.imgur.com/o9ulwJB.png", "name": "Low Poly Stock Car Asset", "tags": ["3D Model"]},
        {"image": "https://i.imgur.com/ZfVTIDy.png", "name": "2022 WAS Power Ranking", "tags": ["Digital Art"]},
        {"image": "https://i.imgur.com/Grm9L3A.png", "name": "DallasMed85 Avatar", "tags": ["Digital Art"]},
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
        {"image": "https://i.imgur.com/vpN6EAE.png", "name": "Character Select Screen Concept", "tags": ["Concept Art"]}

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
    <div class="gridContainer">
        {#each projects as project}
            <div class="textPanel">
                <div class="imgWrapper" on:click={() => {toggleModal(); updateModal(project.image, "");}} on:keypress={() => {toggleModal(); updateModal(project.image, "");}}>
                    <img src="{project.image}" alt="{project.name}">
                </div>
                <p class="name">{project.name}</p>
                <div class="tags">
                    {#each project.tags as tag}
                        <p class="tag">{tag}</p>
                    {/each}
                </div>
            </div>
        {/each}
    </div>

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

    .textPanel {
        display: grid;
        justify-items: center;
        align-items: center;
    }
    .textPanel:hover img, .textPanel:active img {
        box-shadow: 0 0 20px 0.5em rgba(0, 0, 0, 0.2);
        transform: rotate3d(0, 0, 0, 0) rotate(0);

    }
    
    .textPanel img {
        width: 100%;
        height: auto;
        transition: 0.5s;

        transform: rotate3d(.5,-.866,0,15deg) rotate(1deg);
    }

    .imgWrapper {
        display: grid;
        justify-items: center;
        align-items: center;
        aspect-ratio: 1 / 1;
    }

    .name {
        color: rgba(60, 77, 242, 1.0);
        padding: 1em;
    }

    .tags {
        display: inline-flex;
    }

    .tag {
        color: white;
        background-color: #84253b;
        border-radius: 0.5em;
        padding: 0.3em;
        font-size: 0.9em;
        display: inline-block;
        margin: 0.1em;
    }
</style>