<script>
    export let caption;
    export let maplink;
    export let imgSrc;
    export let imgAlt;
</script>

<div>
    {#if caption}
        <h3>{caption}</h3>
    {/if}
    <iframe 
        src={maplink} 
        allowfullscreen="" loading="lazy" referrerpolicy="no-referrer-when-downgrade" title="map">
    </iframe>
</div>

<noscript>
    <div>
        {#if caption}
            <h3>{caption}</h3>
        {/if}
        <img src={imgSrc} alt={imgAlt}/>
    </div>
</noscript>

<style>

    :root {
        --map-justify-self: center;
        --map-iframe-width: 500px;
        --map-iframe-height: 500px;
    }

    div {
        justify-self: var(--map-justify-self)
    }

    iframe {
        border: 0;
        border-radius: 3px;
        width: var(--map-iframe-width);
        height: var(--map-iframe-height);
        max-width:100%;
    }

    img {
        border-radius: 3px;
        width: var(--map-iframe-width);
        height: var(--map-iframe-height);
        object-fit: cover;
    }

    h3 {
        width: var(--map-iframe-width);
    }

</style>