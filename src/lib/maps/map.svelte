<script>
    export let maplink;
</script>

<iframe 
    src={maplink} 
    allowfullscreen="" loading="lazy" referrerpolicy="no-referrer-when-downgrade" title="map">
</iframe>

<style>

    :root {
        --map-iframe-width: 500px;
        --map-iframe-height: 500px;
        --map-iframe-justify-self: end;
    }

    iframe {
        border: 0;
        border-radius: 3px;
        width: var(--map-iframe-width);
        height: var(--map-iframe-height);
        justify-self: var(--map-iframe-justify-self);
    }
</style>