<script>

    export let title = {title: 'Title Ipsum', href: './'}
    export let links = [
        {linkTitle: 'Link Ipsum', href: './'}, 
        {linkTitle: 'Link Ipsum', href: './'}, 
        {linkTitle: 'Link Ipsum', href: './'} 
    ]
    export let callToAction = 'Call To Action'
    export let displayCallToAction = true
    export let imageSource = ''
    export let altText = ''

    let activeLink
    let y

</script>

<svelte:window bind:scrollY={y} />

<header class="{y > 0 ? 'scrolled' : ''}">
    <div>
        <h1>
            <a href={title.href}>
                <img src={imageSource} alt={altText}>
                {title.title}
            </a>
        </h1>
        <nav>
            {#each links as link, i}
                <a href={link.href} class={activeLink === `link${i}` ? 'active' : ''} on:click={() => activeLink = `link${i}`}>{link.linkTitle}</a>
            {/each}
            {#if displayCallToAction==true}
                <a href="./" class="call-to-action" 
                on:click={() => activeLink = ''}>{callToAction}</a>
            {/if}
        </nav>
    </div>
</header>

<style>

    :root {
        --background-color: white;
        --scroll-color: white;
        --color-main: black;
        --color-second: white;
        --color-accent: cornflowerblue;
        --width: ;
        --py: 0px;
        --px: 20px;
        --gap: 50px;
        --margin: auto;
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

    header > div > * {
        flex-grow: 1;
    }

    img {
        width: 75px;
        height: 75px;
    }

    header > div > h1 > a {
        width: fit-content;
        display: flex;
        align-items: center;
        gap: 10px;
    }

    header > div > nav {
        display: flex;
        align-items: center;
        justify-content: flex-end;
        gap: var(--gap);
    }

    header > div > nav > a {
        padding: 8px;
    }

    header > div > nav > a:hover {
        margin-bottom: -3px;
        border-bottom: 3px solid var(--color-accent);
    }

    .call-to-action {
        text-align: center;
        padding: 15px 30px;
        border-radius: 5px;
        background-color: var(--color-accent);
        color: var(--color-second);
    }

    .call-to-action:hover {
        margin-bottom: unset;
        border-bottom: unset;
        outline: 3px solid var(--color-main);
    }

    .active {
        margin-bottom: -3px;
        border-bottom: 3px solid var(--color-accent);
    }

</style>