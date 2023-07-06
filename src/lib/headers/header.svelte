<script>
    import Hamburger from '../menus/hamburger.svelte';
    import Hamburger2 from '../menus/hamburger2.svelte';

    export let title = {title: 'Title Ipsum', href: './'}
    export let imageSource = ''
    export let altText = ''

    export let links = [
        {linkTitle: 'Link Ipsum', href: './'}, 
        {linkTitle: 'Link Ipsum', href: './'}, 
        {linkTitle: 'Link Ipsum', href: './'} 
    ]

    export let callToAction = {linkTitle: 'Call To Action', href: './'}
    export let displayCallToAction = true

    export let hamburgerType = 1;

    let y
    let activeLink

</script>

<svelte:window bind:scrollY={y} />

<header class="{y > 0 ? 'scrolled' : ''}">
    <div>
        <h2>
            <a href={title.href}>
                <img src={imageSource} alt={altText}>
                {title.title}
            </a>
        </h2>
        <nav>
            {#each links as link, i}
                <a href={link.href} class={activeLink === `link${i}` ? 'active' : ''} on:click={() => activeLink = `link${i}`}>{link.linkTitle}</a>
            {/each}
        </nav>
        {#if displayCallToAction==true}
            <div class="call-to-action-wrapper">
                <!-- <a href="./" class="call-to-action-secondary">Button Ipsum</a> Keep working later --> 
                <a href={callToAction.href} class="call-to-action" 
                on:click={() => activeLink = ''}>{callToAction.linkTitle}</a>
            </div>
        {/if}
        {#if hamburgerType == 1}
            <div class="hamburger-menu">
                <Hamburger 
                    links = {links}
                />
            </div>
        {/if}
        {#if hamburgerType == 2}
            <div class="hamburger-menu">
                <Hamburger2 
                    links = {links}
                />
            </div>
        {/if}
    </div>
</header>

<style>
    
    :root {
        --width: ;
        --py: 0px;
        --px: 20px;
        --gap: 50px;
        --margin: auto;
        --coa-pos: flex-end;
        --coa-flex-grow: 0;
        --nav-px: 25px;
        --h2-flex-grow: 1;
    }

    a {
        text-decoration: unset;
        color: unset;
    }

    header {
        padding: var(--py) var(--px);
        top: 0;
        position: sticky;
        background-color: var(--background-color);
        color: var(--color-main);
        font-weight: bold;
        z-index: 9999;
        transition: background-color .2s;
    }

    .scrolled {
		background-color: var(--scroll-color);
        transition: background-color .2s;
	}

    header > div {
        display: flex;
        align-items: center;
        margin: var(--margin);
        width: var(--width);
    }

    img {
        width: 75px;
        height: 75px;
    }

    header > div > h2 {
        flex-grow: var(--h2-flex-grow);
    }

    header > div > h2 > a {
        width: fit-content;
        display: flex;
        align-items: center;
        gap: 10px;
    }

    header > div > nav {
        display: flex;
        align-items: center;
        justify-content: center;
        gap: var(--gap);
        padding: 0 var(--nav-px);
    }

    header > div > nav > a {
        width: fit-content;
        font-weight: bold;
        padding: 8px;
        color: var(--color-main);
        text-decoration: none;
    }

    header > div > nav > a:hover, .active {
        border-bottom: 3px solid var(--color-accent);
        margin-bottom: -3px;
    }

    .call-to-action-wrapper {
        flex-grow: var(--coa-flex-grow);
        display: flex;
        gap: 25px;
        justify-content: var(--coa-pos);
        align-items: center;
    }

    .call-to-action {
        text-align: center;
        padding: 15px 30px;
        border-radius: 5px;
        background-color: var(--color-accent);
        color: var(--color-second);
    }

    /*
    .call-to-action-secondary {
        text-align: center;
        padding: 15px 30px;
        border-radius: 5px;
        color: var(--color-main);
        box-shadow: inset 0px 0px 0px 3px var(--color-accent);
    }
    */

    .call-to-action:hover {
        margin-bottom: unset;
        border-bottom: unset;
        outline: 3px solid var(--color-main);
    }

    .hamburger-menu {
        display: none;
    }

    /* set multiple breakpoints for different screen sizes? */
    @media screen and (max-width: 1200px) {
        header > div > nav {
            display: none;
        }

        .call-to-action-wrapper {
            display: none;
        }
        .hamburger-menu {
            display: unset;
        }
    }

</style>