<script>    
    // Use to allow custom classes and styles
    export let className = '';
    export let unsetCSS = false;  
    let defaultClass = unsetCSS ? '' : 'header';
    export let style;

    // Custom Values
    let y

</script>

<svelte:window bind:scrollY={y} />

<header class="{y > 0 ? 'scrolled' : ''} {defaultClass} {className}" style="{style}">
    <div>
        <slot></slot>
    </div>
</header>

<style>

    .header {
        padding: var(--padding, 10px 20px);
        top: 0;
        position: sticky;
        background-color: var(--background-color);
        color: var(--color-main);
        font-weight: bold;
        z-index: 9999;
        transition: background-color .2s;
    }

    .scrolled {
		background-color: var(--scroll-color, white);
        transition: background-color .2s;
	}

    header > div {
        display: flex;
        align-items: center;
        justify-content: var(--justify-content, space-between);
        margin: var(---margin, auto);
        width: var(--width);
    }

</style>
