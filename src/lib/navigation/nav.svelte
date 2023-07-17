<script>
    export let caption = ''
    export let links = [
        {linkTitle: 'Read More', href: './'},
        {linkTitle: 'Read More', href: './'},
        {linkTitle: 'Read More', href: './'},
        {linkTitle: 'Read More', href: './'},
    ]
</script>

{#if caption}
    <h2>{caption}</h2>
{/if}
<nav>
    {#each links as link, i}
        <a href={link.href}>{link.linkTitle}</a>
    {/each}        
</nav>  

<style>

    :root {
        --nav-nav-flex-direction: column;
    }

    nav {
        --gap: 10px;
        display: flex;
        flex-direction: var(--nav-nav-flex-direction);
        gap: var(--gap);
    }

</style>
