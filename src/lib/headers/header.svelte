<script>
    import Link from '../links/link.svelte'
    import Hamburger from '../menus/hamburger.svelte';

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

    let y
    let activeLink

</script>

<svelte:window bind:scrollY={y} />

<header class="{y > 0 ? 'scrolled' : ''}">
    <div>
        <Hamburger></Hamburger>
        <!--
        <div id="menuToggle">
            <input type="checkbox" />
            <span></span>
            <span></span>
            <span></span>
            <ul id="menu">
                {#each links as link, i}
                    <Link 
                        text={link.linkTitle} 
                        href={link.href} 
                    />
                    <a href={link.href} class={activeLink === `link${i}` ? 'active' : ''} on:click={() => activeLink = `link${i}`}>{link.linkTitle}</a>
                {/each}
            </ul>
        </div>
        -->
        <h2>
            <a href={title.href}>
                <img src={imageSource} alt={altText}>
                {title.title}
            </a>
        </h2>
        <nav>
            {#each links as link, i}
            <!-- 
                <Link 
                    text={link.linkTitle} 
                    href={link.href} 
                />-->
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

    header > div > nav > a, header > div > div > ul > a {
        width: fit-content;
        font-weight: bold;
        padding: 8px;
        color: var(--color-main);
        text-decoration: none;
    }

    header > div > nav > a:hover, header > div > div > ul > a:hover, .active {
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

    /* Hamburger menu */

    #menuToggle {
        z-index: 9999;
        display: none;
        position: relative;
        -webkit-user-select: none;
        user-select: none;
        border-radius: 10px;
        padding: 25px;
    }
    
    #menuToggle input {
        z-index: 9999;
        display: block;
        width: 40px;
        height: 32px;
        position: absolute;
        top: -7px;
        left: -5px;
        cursor: pointer;
        opacity: 0;
        -webkit-touch-callout: none;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
    }
    
    #menuToggle span {
        z-index: 9998;
        display: block;
        width: 33px;
        height: 4px;
        margin-bottom: 5px;
        position: relative;
        top: 50%;
        left: 50%;
        transform: translate(-50%, 50%);
        background: var(--color-main);
        border-radius: 3px;
        transform-origin: 4px 0px;  
        transition: transform 0.5s cubic-bezier(0.77,0.2,0.05,1.0),
                    background 0.5s cubic-bezier(0.77,0.2,0.05,1.0),
                    opacity 0.55s ease;
    }
    
    #menuToggle span:first-child {
        transform-origin: 0% 0%;
    }
    
    #menuToggle span:nth-last-child(2) {
        transform-origin: 0% 100%;
    }
    
    #menuToggle input:checked ~ span {
        opacity: 1;
        transform: rotate(45deg) translate(-2px, -1px);
        background: black;
    }
    
    #menuToggle input:checked ~ span:nth-last-child(3) {
        opacity: 0;
        transform: rotate(0deg) scale(0.2, 0.2);
    }
    
    #menuToggle input:checked ~ span:nth-last-child(2) {
        transform: rotate(-45deg) translate(0, -1px);
    }
    
    #menu {
        position: absolute;
        width: 100vw;
        height: 100vh;
        margin: -100px 0 0 -50px;
        padding: 50px;
        padding-top: 125px;
        display: flex;
        flex-direction: column;
        gap: 25px;
        background: var(--color-second);
        list-style-type: none;
        -webkit-font-smoothing: antialiased;
        /* to stop flickering of text in safari */
        transform-origin: 0% 0%;
        transform: translate(-100%, 0);
        transition: transform 0.5s cubic-bezier(0.77,0.2,0.05,1.0);
    }
    
    #menuToggle input:checked ~ ul {
        transform: none;
    }

    @media screen and (max-width: 1200px) {
        header > div > nav {
            display: none;
        }

        .call-to-action-wrapper {
            display: none;
        }

        #menuToggle {
            display: block;
        }
    }

</style>