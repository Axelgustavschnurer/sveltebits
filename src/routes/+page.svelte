<script>
    import Header from '../lib/headers/header.svelte'
    import Footer from '../lib/footers/footer.svelte'
    import Map from '../lib/maps/map.svelte';
</script>

<Header 
    imageSource="./logo.svg"
    title={{title: 'Title Ipsum', href: './'}}
    callToAction={{linkTitle: 'Button Ipsum', href: './'}}
    links={[
        {linkTitle: 'Read More', href: './'},
        {linkTitle: 'Read More', href: './'},
        {linkTitle: 'Read More', href: './'},
        {linkTitle: 'Read More', href: './'},
    ]}
    hamburgerType=1
    --scroll-color=white
    --h2-flex-grow=1
    --coa-flex-grow=1
    --width=80%
    --background-color=transparent
/>


<main style="height: 200vh;">
</main>

<Footer>
    <div style="display: flex; flex-direction:column;gap:15px;width:250px;heigth:250px;max-width:100%;">
        <h3>Nånting</h3>
        <a href="./">Test</a>
        <a href="./">Test</a>
        <a href="./">Test</a>
    </div>
    <div style="display: flex; flex-direction:column;gap:15px;width:250px;heigth:250px;max-width:100%;">
        <h3>Nånting</h3>
        <a href="./">Test</a>
        <a href="./">Test</a>
        <a href="./">Test</a>
    </div>
    <Map 
        title="Hitta Hit"
        maplink="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d2003.643913210977!2d17.641078303692144!3d59.85505366110544!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x465fcbfa5cde33e5%3A0xbc997b521e4c610c!2sIslandsbron!5e0!3m2!1sen!2sse!4v1688670915402!5m2!1sen!2sse"
        --map-iframe-width=250px
        --map-iframe-height=250px
    />
</Footer>

<style>
    :global(body) {
        margin: 0;
        background: linear-gradient(180deg, lightpink -10%, lightblue);
    }
</style>
