<script>
    import { fade } from 'svelte/transition';
    import { slide } from 'svelte/transition';

    export let links = [
        {"route": "/", "text": "Home"}
    ];

    let menuShown = false;

    let toggleMenu = () => {
        menuShown = !menuShown
    };
</script>

<nav href="top">
    <div id="header">
        <div class="container">
            <a href="/"><img id="siteLogo" src="/logo.png" alt="Logo"></a>
            <button id="navOpen" on:click={toggleMenu}>
                {#if menuShown}
                    <p transition:slide style="transform: rotate(45deg)">+</p>
                {:else}
                    <p transition:slide>=</p>
                {/if}
            </button>
        </div>
    </div>
    {#if menuShown}
        <div class="dropdown" transition:slide>
            <!-- <button class="modalButton">X</button> -->
            <div class="container gridContainer">
                {#each links as link}
                    <a class="modalLink" href="{link.route}">{link.text}</a>
                {/each}
            </div>
        </div>
    {/if}
</nav>

<!--Place modal above header bar to make header visible while modal is open-->
<!--Need to refactor so menu acknowledges header bar-->
<!-- <div id="navMenu" class="modal" transition:slide>
    <div class="modalContent">
        <a class="modalLink" href="/">Home</a>
        <a class="modalLink" href="#">Pricing</a>
        <a class="modalLink" href="#">About</a>
        <button on:click={toggleMenu} id="navClose" class="modalLink modalButton">Close Menu</button>
    </div>
</div> -->

<style>
    nav {
        z-index: 10;
    }
    .dropdown {
        background-color: rgba(48, 48, 48, 0.98); /*rgba(0, 0, 0, 0.8)*/
    }
    .gridContainer {
        grid-gap: 0;
    }

    .modalLink {
        font-size: 1.2em;
        font-weight: bold;
    }
    
    /* .modalLink:hover, .modalLink:active {
        color: white;
    } */
</style>