<script>
    export let title = 'Your Title Here'
    export let infoText = 'Your Slogan Here'
    export let linkText = 'Link Text'
</script>

<main>
    <div>
        <h1>{title}</h1>
        <p>{infoText}</p>
        <a href="./">{linkText}</a>
    </div>
    <img src="background.png" alt="">
</main>

<style>

    :root {
        --width: ;
    }
    
    * {
        font-family: Arial, Helvetica, sans-serif;
        line-height: 1.5;
    }

    a {
        text-decoration: unset;
        color: unset;
    }

    main {
        padding: 50px;
        margin: auto;
        width: var(--width);
        display: grid;
        grid-template-columns: 1fr 1fr;
    }

    main > img {
        height: 500px;
    }

    main > div > h1 {
        font-size: 3rem;
        margin-block-end: 0;
    }

    main > div > p {
        margin-block-start: 0;
        font-size: 1.5rem;
    }

    main > div > a {
        padding: 8px
    }

    main > div > a:hover {
        margin-bottom: -3px;
        border-bottom: 3px solid var(--color-accent);
    }

</style>