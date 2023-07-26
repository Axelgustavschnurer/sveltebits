<script>
    export let caption = ''
    export let links = [
        {linkTitle: 'Read More', href: './'},
        {linkTitle: 'Read More', href: './'},
        {linkTitle: 'Read More', href: './'},
    ]
</script>

<div>
    {#if caption}
        <h3>{caption}</h3>
    {/if}
    <nav>
        {#each links as link, i}
            <a href={link.href}>{link.linkTitle}</a>
            {#if typeof link === 'Array'}
                {#each link as sublink}
                    <p>TEST</p>
                {/each}
            {/if}
        {/each}        
    </nav>  
</div>

<style>

    :root {
        --nav-padding: ;
        --nav-justify-self: center;
        --nav-font-weight: ;
        --nav-text-decoration: ;
        --nav-gap: 10px;
        --nav-width: ;
        --nav-height: ;

        --nav-nav-flex-direction: column;

        --nav-a-padding: ;
    }

    div {
        width: var(--nav-width);
        height: var(--nav-height);
        padding: var(--nav-padding);
        justify-self: var(--nav-justify-self);
    }

    nav {
        display: flex;
        flex-direction: var(--nav-nav-flex-direction);
        gap: var(--nav-gap);
    }

    a, a:active, a:visited, a:active {
        color: var(--color-main);
        font-weight: var(--nav-font-weight);
        text-decoration: var(--nav-nav-flex-direction);
        padding: var(--nav-a-padding)
    }

    a:hover {
        margin-bottom: -3px;
        border-bottom: 3px solid var(--color-accent);
    }

</style>
