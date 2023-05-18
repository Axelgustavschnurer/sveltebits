<script>
    let activeLink = '';

    function setActive(link) {
        activeLink = link;
    }

    function removeActiveClass() {
        activeLink = null;
    } 

    export let title = 'Title Ipsum'
    export let links = ['Link Ipsum', 'Link Ipsum', 'Link Ipsum']
    export let callToAction = 'Call To Action'
    export let imageSource = 'logo.svg'
    export let displayCallToAction = true

</script>

<header>
    <h1>
        <a href='./'>
            <img src={imageSource} alt="">
            {title}
        </a>
    </h1>
    <nav>
        {#each links as link, i}
            <a href="./" class={activeLink === `link${i}` ? 'active' : ''} on:click={() => setActive(`link${i}`)}>{link}</a>
        {/each}
        {#if displayCallToAction==true}
            <a href="./" class="call-to-action" on:click={removeActiveClass}>{callToAction}</a>
        {/if}
    </nav>
</header>

<style>

    :root {
        --background-color: white;
        --color-main: black;
        --color-second: white;
        --color-accent: cornflowerblue;
        --width: ;
        --py: 10px;
        --px: 20px;
        --gap: 50px;
        --margin: auto;
    }
    
    * {
        font-family: Arial, Helvetica, sans-serif;
    }

    a {
        text-decoration: unset;
        color: unset;
    }

    header {
        display: flex;
        align-items: center;
        padding: var(--py) var(--px);
        top: 0;
        position: sticky;
        width: var(--width);
        background-color: var(--background-color);
        color: var(--color-main);
        margin: var(--margin);
        font-weight: bold;
    }

    header > * {
        flex-grow: 1;
    }

    img {
        width: 75px;
        height: 75px;
    }

    header > h1 > a {
        width: fit-content;
        display: flex;
        align-items: center;
        gap: 10px;
    }

    header > nav {
        display: flex;
        align-items: center;
        justify-content: flex-end;
        gap: var(--gap);
    }

    header > nav > a {
        padding: 8px;
    }

    header > nav > a:hover {
        margin-bottom: -3px;
        border-bottom: 3px solid var(--color-accent);
    }

    .call-to-action {
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