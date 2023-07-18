<script>

    let y

</script>

<svelte:window bind:scrollY={y} />

<header class="{y > 0 ? 'scrolled' : ''}">
    <div>
        <slot></slot>
    </div>
</header>

<style>
    
    :root {
        --header-scroll-color: white;
        --header-width: ;
        --header-padding: 10px 20px;
        --header-margin: auto;
        --header-justify-content: space-between;
    }

    header {
        padding: var(--header-padding);
        top: 0;
        position: sticky;
        background-color: var(--background-color);
        color: var(--color-main);
        font-weight: bold;
        z-index: 9999;
        transition: background-color .2s;
    }

    .scrolled {
		background-color: var(--header-scroll-color);
        transition: background-color .2s;
	}

    header > div {
        display: flex;
        align-items: center;
        justify-content: var(--header-justify-content);
        margin: var(--header-margin);
        width: var(--header-width);
    }

</style>
