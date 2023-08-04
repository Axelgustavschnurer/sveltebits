<script>
    // Use to allow custom classes and styles
    export let className = '';
    export let unsetCSS = false;  
    let defaultClass = unsetCSS ? '' : 'map';
    export let style;

    // Custom Values
    export let caption;
    export let mapLink;
    export let src;
    export let alt;
    export let address;
    export let addressLink;

</script>

<div class="{defaultClass} {className}" style="{style}">
    {#if caption}
        <h3>{caption}</h3>
    {/if}
    <iframe 
        src={mapLink} 
        allowfullscreen="" loading="lazy" referrerpolicy="no-referrer-when-downgrade" title="map">
    </iframe>
    {#if address}
        <a href="{addressLink}">{address}</a>
    {/if}
</div>

<noscript>
    <div class="{defaultClass} {className}" style="{style}">
        {#if caption}
            <h3>{caption}</h3>
        {/if}
        <img src={src} alt={alt}/>
        {#if address}
            <a href="{addressLink}">{address}</a>
        {/if}
    </div>
</noscript>

<style>

    .map {
        justify-self: var(--justify-self, center);
        display: flex;
        flex-direction: column;
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

    a {
        width: var(--width, 250px);
        color: var(--color-main);
        padding: 10px 0;
    }

</style>