<script>
    export let title;
    export let maplink;
</script>

<div>
    {#if title}
        <h3>{title}</h3>
    {/if}
    <iframe 
        src={maplink} 
        allowfullscreen="" loading="lazy" referrerpolicy="no-referrer-when-downgrade" title="map">
    </iframe>
</div>

<style>

    :root {
        --map-iframe-width: 500px;
        --map-iframe-height: 500px;
        --map-iframe-justify-self: ;
    }

    iframe {
        border: 0;
        border-radius: 3px;
        width: var(--map-iframe-width);
        height: var(--map-iframe-height);
        justify-self: var(--map-iframe-justify-self);
        max-width:100%;
    }

    h3 {
        width: var(--map-iframe-width);
    }

</style>