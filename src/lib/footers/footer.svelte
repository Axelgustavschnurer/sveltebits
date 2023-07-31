<script>    
    // Use to allow custom classes and styles
    export let className = '';
    export let unsetCSS = false;  
    let defaultClass = unsetCSS ? '' : 'footer';
    export let style;
</script>

<footer class="{defaultClass} {className}" style="{style}">
    <slot></slot>
</footer>

<style>

    .footer {
        border-top: 6px solid var(--color-accent);
        padding: 25px;
        background-color: var(--background-color);

        display: grid;
        grid-template-columns: var(--grid-template-columns, repeat(auto-fit, minmax(250px, 1fr)));
        grid-auto-rows: auto;
        justify-items: center;
        gap: var(--gap, 15px);
    }

</style>