<script>

</script>

<footer>
    <slot></slot>
</footer>

<style>

    :root {
        --footer-grid-template-columns: 1fr 1fr 1fr;
    }

    footer {
        border-top: 6px solid var(--color-accent);
        padding: 25px;
        background-color: var(--background-color);

        display: grid;
        grid-template-columns: var(--footer-grid-template-columns);
        grid-auto-rows: auto;
        place-items: center;
        gap: 15px;
    }

</style>