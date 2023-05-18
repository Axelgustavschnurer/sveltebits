<script>
    import Header from '../lib/headers/header.svelte'
    import Footer from '../lib/footers/footer.svelte'
    import Homepage from '../lib/page-content/homepage.svelte'
</script>

<Header 
    title='SvelteBits'
    links={['Learn More']}
    callToAction='Download The Package'
    --width=80%
    --background-color=transparent
/>

<Homepage 
    title='SvelteBits UI Library'
    infoText='SvelteBits is the npm package making your life as a web developer easier. Create stunning websites in seconds without having to worry responsivness.'
    linkText='Read More'
    --width=80%
/>

<Footer />

<style>
    :global(body) {
        margin: 0;
    }
</style>
