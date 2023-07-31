<script>
    // Use to allow custom classes and styles
    export let className = '';
    export let unsetCSS = false;  
    let defaultClass = unsetCSS ? '' : 'map';
    export let style;

    // Custom Values
    export let caption;
    export let maplink;
    export let imgSrc;
    export let imgAlt;

</script>

<div class={`${defaultClass} ${className}`} style="{style}">
    {#if caption}
        <h3>{caption}</h3>
    {/if}
    <iframe 
        src={maplink} 
        allowfullscreen="" loading="lazy" referrerpolicy="no-referrer-when-downgrade" title="map">
    </iframe>
</div>

<noscript>
    <div class={`${defaultClass} ${className}`} style="{style}">
        {#if caption}
            <h3>{caption}</h3>
        {/if}
        <img src={imgSrc} alt={imgAlt}/>
    </div>
</noscript>

<style>

    .map {
        justify-self: var(--justify-self, center)
    }

    iframe {
        border: 0;
        border-radius: 3px;
        width: var(--width, 250px);
        height: var(--height, 250px);
    }

    img {
        border-radius: 3px;
        width: var(--width, 250px);
        height: var(--width, 250px);
        object-fit: cover;
    }

    h3 {
        width: var(--width, 250px);
    }

</style>