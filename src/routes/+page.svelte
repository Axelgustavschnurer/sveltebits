<script>
    import Header from '../lib/headers/header.svelte'
    import Footer from '../lib/footers/footer.svelte'
    import Map from '../lib/maps/map.svelte';
    import Nav from '$lib/navigation/nav.svelte';
    import Logo from '$lib/images/logo.svelte';
    import CallToAction from '$lib/links/callToAction.svelte';
    import Hamburger from '$lib/menus/hamburger.svelte';
</script>

<Header 
    --width=90%
    --background-color=transparent
>
        <Logo imgAlt="Logo" imgSrc="logo.svg" href="./"
            --img-width=75px --img-height=75px>
            <h3>SvelteBits</h3>
        </Logo>
        <div class="navigation">
            <Nav
                style="width:unset;"
                links={[
                    {linkTitle: 'Read More', href: './'},
                    {linkTitle: 'Read More', href: './'},
                    {linkTitle: 'Read More', href: './'},
                ]}
                --flex-direction=row
                --font-weight=bold
                --a-padding=8px
                --padding="0 20px"
            />
            <CallToAction>Button Ipsum</CallToAction> 
        </div>
        <div class="hamburger-menu">
            <Hamburger links={[
                {linkTitle: 'Read More', href: './'},
                {linkTitle: 'Read More', href: './'},
                {linkTitle: 'Read More', href: './'},
            ]}/>
        </div>
</Header>


<main style="height: 200vh;">
</main>

<Footer>
    <Nav
        caption="Test"
        links={[
            {linkTitle: 'Read More', href: './'},
            {linkTitle: 'Read More', href: './'},
            {linkTitle: 'Read More', href: './'},
            {linkTitle: 'Read More', href: './'},
        ]}
        --width=250px
    />
    <Map 
        className="test"
        src="logo.svg"
        alt="Karta"
        caption="Hitta Hit"
        mapLink="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d2003.643913210977!2d17.641078303692144!3d59.85505366110544!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x465fcbfa5cde33e5%3A0xbc997b521e4c610c!2sIslandsbron!5e0!3m2!1sen!2sse!4v1688670915402!5m2!1sen!2sse"
        address="Test Adress 1"
        addressLink="https://goo.gl/maps/pdsAdVxr1gTWgZ8N7"
        />
</Footer>

<style>
    :global(body) {
        margin: 0;
        background: linear-gradient(180deg, lightpink -10%, lightblue);
    }

    .navigation {
        display: flex;
        align-items: center;
    }

    .hamburger-menu {
        display: none;
    }

    @media screen and (max-width: 800px) {
        .hamburger-menu {
            display: unset;
        }
        .navigation {
            display: none;
        }
    }

</style>
