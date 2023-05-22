<script>
    import Header from '../lib/headers/header.svelte'
    import Footer from '../lib/footers/footer.svelte'
</script>

<Header 
    title='SvelteBits'
    links={['Learn More']}
    callToAction='Download The Package'
    --width=80%
    --background-color=transparent
/>

<Footer />

<style>
    :global(body) {
        margin: 0;
    }
</style>
