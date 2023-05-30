<script>
    export let text = ''
    export let href = ''
</script>

<a href={href}>{text}</a>

<style>

    :root {
        --padding: 8px;
        --font-weight: bold;
        --color: black;
        --accent: cornflowerblue;
    }

    a {
        font-weight: var(--font-weight);
        padding: var(--padding);
        color: var(--color);
        text-decoration: none;
        width: fit-content; /* Maybe not? */
    }

    a:hover {
        border-bottom: 3px solid var(--accent);
        margin-bottom: -3px;
    }

</style>