<script>
    import Header from '../lib/headers/header.svelte'
    import Footer from '../lib/footers/footer.svelte'
</script>

<Header 
    title={{title: 'Title Ipsum', href: './'}}
    callToAction={{linkTitle: 'Button Ipsum', href: './'}}
    links={[
        {linkTitle: 'Read More', href: './'},
        {linkTitle: 'Read More', href: './'},
        {linkTitle: 'Read More', href: './'},
        {linkTitle: 'Read More', href: './'},
    ]}
    --scroll-color=white
    --h2-flex-grow=1
    --coa-flex-grow=1
    --width=80%
    --background-color=transparent
/>


<main style="height: 200vh;">
</main>

<Footer>
    <div class="box">Test Test Test</div>
    <div class="box">Test</div>
    <div class="box">TestTestTestTestTestTestTestTestTestTestTestTestTestTestTestTestTestTestTestTestTestTestTestTest</div>
    <div class="box">Test Test Test</div>
    <div class="box">Test</div>
    <div class="box">TestTestTestTest</div>
    <div class="box">Test Test Test</div>
    <div class="box">Test</div>
    <div class="box">TestTestTestTest</div>
    <div class="box">Test</div>
    <div class="box">TestTestTestTest</div>
    <div class="box">Test Test Test</div>
    <div class="box">Test</div>
    <div class="box">TestTestTestTest</div>
    <div class="box">Test</div>
    <div class="box">TestTestTestTest</div>
    <div class="box">Test Test Test</div>
    <div class="box">Test</div>
    <div class="box">TestTestTestTest</div>
</Footer>

<style>
    :global(body) {
        margin: 0;
        background: linear-gradient(180deg, lightpink -10%, lightblue);
    }

    .box {
        background-color: red;
        padding: 25px;
        border-radius: 5px;
        word-break: break-all;
    }

</style>
