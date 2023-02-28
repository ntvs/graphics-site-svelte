<script>
    //ORIGINAL CODE:
    //on:click={() => {toggleModal(); updateModal(project.image, "");}} on:keypress={() => {toggleModal(); updateModal(project.image, "");}}
    /*
    
    <!-- <div class="textPanel">
        <div class="imgWrapper" on:click={() => {toggleModal(); updateModal(project.image, "");}} on:keypress={() => {toggleModal(); updateModal(project.image, "");}}>
            <img src="{project.image}" alt="{project.name}">
        </div>
        <p class="name">{project.name}</p>
        <div class="tags">
            {#each project.tags as tag}
                <p class="tag">{tag}</p>
            {/each}
        </div>
    </div> -->

    */

    //Event dispatcher
    import { createEventDispatcher } from 'svelte';
    const dispatch = createEventDispatcher();

    export let object = {
        "name": "",
        "image": "",
        "tags": []
    };

</script>

<div class="textPanel" on:click={() => {dispatch('click', {})}} on:keypress={() => {dispatch('keypress', {})}}>
    <div class="imgWrapper">
        <img src="{object.image}" alt="{object.name}">
    </div>
    <p class="name">{object.name}</p>
    <div class="tags">
        {#each object.tags as tag}
            <p class="tag">{tag}</p>
        {/each}
    </div>
</div>

<style>
    .textPanel {
        display: grid;
        justify-items: center;
        align-items: center;
    }
    .textPanel:hover img, .textPanel:active img {
        box-shadow: 0 0 20px 0.5em rgba(0, 0, 0, 0.2);
        transform: rotate3d(0, 0, 0, 0) rotate(0);
        -webkit-transform: rotate3d(0, 0, 0, 0) rotate(0);

    }
    
    .textPanel img {
        width: 100%;
        height: auto;
        transition: 0.5s;

        transform: rotate3d(.5,-.866,0,15deg) rotate(1deg);
        -webkit-transform: rotate3d(.5,-.866,0,15deg) rotate(1deg);
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