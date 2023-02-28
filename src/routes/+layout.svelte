<script>
    import NavBar from '../lib/Navbar.svelte';
    import Footer from '../lib/Footer.svelte';

    let links = [
        {"route": "/", "text": "Home"},
        {"route": "/work", "text": "Work"},
        {"route": "/", "text": "Pricing"},
        {"route": "/", "text": "About"},
    ]
</script>

<NavBar links={links} />

<slot />

<Footer />