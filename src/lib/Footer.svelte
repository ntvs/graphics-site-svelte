<script>
    import SocialLink from "./SocialLink.svelte";
</script>

<footer>
    <div class="container">
        <!--ntvs is a graphic designer and artist who has been active since 2012. Please use Twitter to contact.-->
        <a href="#top" class="top">Back to the top</a>
        <!-- <h3>&copy; 2012 till infinity</h3> -->
        <SocialLink options={{"icon": "https://png.pngtree.com/png-vector/20221018/ourmid/pngtree-twitter-social-media-round-icon-png-image_6315985.png", "link": "https://twitter.com/TiltStick", "text": "Twitter"}} />
        <!-- <a href="https://twitter.com/TiltStick">Twitter @TiltTtick</a> -->
    </div>
</footer>

<style>
    .top {
        color: rgb(255, 247, 0) !important;
    }

    footer a {
        display: block;
        padding: 1em;
    }
</style>