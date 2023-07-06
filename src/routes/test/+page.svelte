<script>
    import Hamburger2 from "../../lib/menus/hamburger2.svelte";
    import Map from "../../lib/maps/map.svelte"
</script>

<header style="position: sticky; top: 0; display: flex; flex-direction: row-reverse;">
    <Hamburger2
        --hamburger2-py=100px
        --hamburger2-px=25px
        --hamburger2-height=100vh
        --hamburger2-nav-left=initial
    />
</header>

<main style="height: 200vh;">
    <Map 
        maplink="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d2003.643913210977!2d17.641078303692144!3d59.85505366110544!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x465fcbfa5cde33e5%3A0xbc997b521e4c610c!2sIslandsbron!5e0!3m2!1sen!2sse!4v1688670915402!5m2!1sen!2sse"
    />
</main>
