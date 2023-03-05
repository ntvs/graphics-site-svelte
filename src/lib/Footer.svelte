<script>
    import SocialLink from "./SocialLink.svelte";
</script>

<footer>
    <div class="container">
        <a href="#top" class="top">Back to the top</a>
        <!-- <SocialLink options={{"icon": "https://png.pngtree.com/png-vector/20221018/ourmid/pngtree-twitter-social-media-round-icon-png-image_6315985.png", "link": "https://twitter.com/TiltStick"}} /> -->
    </div>
</footer>

<style>
    .top {
        color: /*rgb(255, 247, 0)*/ rgb(136, 136, 136) !important;
    }

    footer a {
        display: block;
        padding: 1em;
    }
</style>