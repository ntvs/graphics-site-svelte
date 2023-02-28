<!--Works, but causes massive lag when animating visibility of any sort-->

<script>
    //Event dispatcher
    import { createEventDispatcher } from 'svelte';
    const dispatch = createEventDispatcher();

    function closeModal(e) {
        dispatch('close', {});
    }

    export let image = "";
    export let alt = "";
</script>

<div class="modal"on:click={closeModal} on:keypress={closeModal}>
    <!-- <button class="closeButton">Close</button> -->
    <div class="container">
        <img src="{image}" alt="{alt}">
    </div>
</div>

<style>
    /* .closeButton {
        position: absolute;
        bottom: 5vh;
        right: 100vw/2;
        font-size: 2em;

        padding: 0.6em;
        border-radius: 1em;
        cursor: pointer;

        color: gray;
        border: none;
        background: none;

        transition: 0.5s;
    }

    .closeButton:hover, .closeButton:active {
        color: white;
    } */

    img {
        max-width: 100%;
        max-height: 80vh;
    }
</style>