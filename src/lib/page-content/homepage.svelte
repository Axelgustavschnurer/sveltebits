<script>
    export let title = 'Your Title Here'
    export let infoText = 'Your Slogan Here'
    export let linkText = 'Link Text'
</script>

<div style="position: relative;">
    <main>
        <div>
            <h1>{title}</h1>
            <p>{infoText}</p>
            <a href="./" style="background-color: indianred;color:white;padding:15px 30px;border-radius:5px;">{linkText}</a>
        </div>
        <img src="background.png" alt="">
    </main>
    <img src="wave.svg" alt="" style="position: absolute; bottom:0;left:0;z-index:0;"/>
</div>

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
        position: relative;
        z-index: 1;
        padding: 150px 50px;
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