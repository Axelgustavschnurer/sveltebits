<script>
    // Use to allow custom classes and styles
    export let className = '';
    export let unsetCSS = false;  
    let defaultClass = unsetCSS ? '' : 'navigation';
    export let style;

    // Custom Values
    export let caption = ''
    export let links = [
        {linkTitle: 'Read More', href: './'},
        {linkTitle: 'Read More', href: './'},
        {linkTitle: 'Read More', href: './'},
    ]
</script>

<div class="{defaultClass} {className}" style="{style}">
    {#if caption}
        <h3>{caption}</h3>
    {/if}
    <nav>
        {#each links as link, i}
            <a href={link.href}>{link.linkTitle}</a>
        {/each}        
    </nav>  
</div>

<style>

    .navigation {
        width: var(--width);
        height: var(--height);
        padding: var(--padding);
        justify-self: var(--justify-self, center);
    }

    nav {
        display: flex;
        font-weight: var(--font-weight);
        flex-direction: var(--flex-direction, column);
        gap: var(--gap, 10px);
    }

    a, a:active, a:visited, a:active {
        color: var(--color-main);
        text-decoration: var(--text-decoration);
        padding: var(--a-padding);
        width: fit-content;
    }

    a:hover {
        margin-bottom: -3px;
        border-bottom: 3px solid var(--color-accent);
    }

</style>
