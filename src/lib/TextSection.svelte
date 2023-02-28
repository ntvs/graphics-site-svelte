<script>
    export let options = {
        "heading": "",
        "text": "",
        "backgroundColor": "",
        "headingColor": "",
        "textColor": "",
        "anchor": ""
    };
</script>

<div class="textSection" style="background: {options.backgroundColor}" id="{options.anchor}">
    <div class="container">
        <h1 style="color: {options.headingColor}">{options.heading}</h1>
        <p style="color: {options.textColor}">{options.text}</p>
    </div>
</div>

<style>
    .textSection {
        padding: 5em 1em;
        transition: 0.5s;
    }

    h1 {
        font-size: 5em;
    }

    p {
        padding: 1em 0;
        font-size: 1.3em;
        line-height: 1.6em;
    }
</style>