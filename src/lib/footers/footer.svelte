<script>

</script>

<footer>
    <slot></slot>
</footer>

<style>

    :root {
        --footer-grid-template-columns: repeat(auto-fit, minmax(250px, 1fr)); /* Min width should be variable but nothing else i think? */
    }

    footer {
        border-top: 6px solid var(--color-accent);
        padding: 25px;
        background-color: var(--background-color);

        display: grid;
        grid-template-columns: var(--footer-grid-template-columns);
        grid-auto-rows: auto;
        justify-content: center;
        gap: 15px;
    }

</style>