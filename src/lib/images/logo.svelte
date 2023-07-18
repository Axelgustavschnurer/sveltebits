<!-- Component for a logo image which may have text accompanying it -->

<script>

    export let href;
    export let imgSrc;
    export let imgAlt;

</script>

<div>
    <a href={href}>
        <img src={imgSrc} alt={imgAlt}>
        <slot></slot>
    </a>
</div>

<style>
    :root {
        --logo-padding: ;
        --logo-flex-direction: row;
        --logo-align-items: center;
        --logo-justify-content: ;
        --logo-gap: ;

        --logo-img-width: 50px;
        --logo-img-height: 50px;
        --logo-img-object-fit: contain;
    }

    a, a:active, a:visited, a:active {
        color: var(--color-main);
        text-decoration: none;
    }

    a {
        padding: var(--logo-padding);
        display: flex;
        flex-direction: var(--logo-flex-direction);
        align-items: var(--logo-align-items);
        justify-content: var(--logo-justify-content);
        gap: var(--logo-gap);   
    }

    img {
        width: var(--logo-img-width);
        height: var(--logo-img-width);
        object-fit: var(--logo-img-object-fit);
    }

</style>