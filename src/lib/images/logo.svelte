<!-- Component for a logo image which may have text accompanying it -->

<script>
    // Use to allow custom classes and styles
    export let className = '';
    export let unsetCSS = false;  
    let defaultClass = unsetCSS ? '' : '';
    export let style;

    // Custom Values
    export let href;
    export let imgSrc;
    export let imgAlt;

</script>

<div class={`${defaultClass} ${className}`} style="{style}">
    <a href={href}>
        <img src={imgSrc} alt={imgAlt}>
        <slot></slot>
    </a>
</div>

<style>

    a, a:active, a:visited, a:active {
        color: var(--color-main);
        text-decoration: none;
    }

    a {
        padding: var(--padding);
        display: flex;
        flex-direction: var(--flex-direction, row);
        align-items: var(--align-items, center);
        justify-content: var(--justify-content);
        gap: var(--gap);   
    }

    img {
        width: var(--img-width, 50px);
        height: var(--img-width, 50px);
        object-fit: var(--img-object-fit, contain);
    }

</style>