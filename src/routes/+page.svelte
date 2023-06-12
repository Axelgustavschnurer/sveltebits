<script>
    import Header from '../lib/headers/header.svelte'
    import Hamburger from '../lib/menus/hamburger.svelte';
    import Footer from '../lib/footers/footer.svelte'
</script>

<header style="position: sticky;">
    <Hamburger></Hamburger>
</header>
<!--
<Header 
    title={{title: 'Title Ipsum', href: './'}}
    callToAction={{linkTitle: 'Button Ipsum', href: './'}}
    links={[
        {linkTitle: 'Read More', href: './'},
        {linkTitle: 'Read More', href: './'},
        {linkTitle: 'Read More', href: './'},
        {linkTitle: 'Read More', href: './'},
    ]}
    --h2-flex-grow=1
    --coa-flex-grow=1
    --width=80%
    --background-color=transparent
/>-->


<main style="height: 200vh;">
</main>

<Footer />

<style>
    :global(body) {
        margin: 0;
        background: linear-gradient(180deg, lightpink -10%, lightblue);
    }

    :global(*) {
        font-family: Arial, Helvetica, sans-serif;
    }

</style>
