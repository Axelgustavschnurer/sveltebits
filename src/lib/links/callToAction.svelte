<script>
    // Use to allow custom classes and styles
    export let className = '';
    export let unsetCSS = false;  
    let defaultClass = unsetCSS ? '' : 'call-to-action';
    export let style;

    // Custom Values
    export let href = './'
</script>

<a href={href} class="{defaultClass} {className}" style="{style}">
    <slot></slot>
</a>

<style>

    a, a:active, a:visited, a:active {
        color: var(--color-second);
        text-decoration: none;
    }

    .call-to-action {
        text-align: center;
        padding: var(--padding, 15px 30px);
        border-radius: var(--border-radius, 5px);
        background-color: var(--color-accent);
        color: var(--color-second);
    }

    .call-to-action:hover {
        margin-bottom: unset;
        border-bottom: unset;
        outline: 3px solid var(--color-main);
    }
</style>