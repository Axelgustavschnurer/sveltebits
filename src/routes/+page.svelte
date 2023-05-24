<script>
    import Header from '../lib/headers/header.svelte'
    import Footer from '../lib/footers/footer.svelte'
</script>

<Header 
    title={{title: 'Title Ipsum', href: './'}}
    callToAction='Button Ipsum'
    links={[
        {linkTitle: 'Read More', href: './'}
    ]}
    --width=80%
    --background-color=transparent
/>

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
