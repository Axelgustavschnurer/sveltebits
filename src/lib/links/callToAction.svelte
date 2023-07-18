<script>
    export let href = './'
</script>

<a href={href} class="call-to-action"><slot></slot></a>

<style>

    a, a:active, a:visited, a:active {
        color: var(--color-second);
        text-decoration: none;
    }

    .call-to-action {
        text-align: center;
        padding: 15px 30px;
        border-radius: 5px;
        background-color: var(--color-accent);
        color: var(--color-second);
    }

    .call-to-action:hover {
        margin-bottom: unset;
        border-bottom: unset;
        outline: 3px solid var(--color-main);
    }
</style>