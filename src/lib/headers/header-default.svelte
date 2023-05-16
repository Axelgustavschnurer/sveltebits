<script>
    let activeLink = '';

    function setActive(link) {
        activeLink = link;
    }

    function removeActiveClass() {
        activeLink = null;
    }
</script>

<header>
    <div>
        <img src="" alt="">
        <h1><a href='./'>Title Ipsum</a></h1>
    </div>
    <nav>
        <a href="./" class={activeLink === 'link1' ? 'active' : ''} on:click={() => setActive('link1')}>Link Ipsum</a>
        <a href="./" class={activeLink === 'link2' ? 'active' : ''} on:click={() => setActive('link2')}>Link Ipsum</a>
        <a href="./" class={activeLink === 'link3' ? 'active' : ''} on:click={() => setActive('link3')}>Link Ipsum</a>
        <a href="./" class="call-to-action" on:click={removeActiveClass}>Link Ipsum</a>
    </nav>
</header>

<style>
    
    * {
        font-family: Arial, Helvetica, sans-serif;
    }

    a {
        text-decoration: unset;
        color: unset;
    }

    header {
        display: flex;
        align-items: center;
        padding: 10px 20px;
        top: 0;
        position: sticky;
        box-shadow: 0 0 10px gray;
    }

    header > * {
        flex-grow: 1;
    }

    img {
        width: 50px;
        height: 50px;
    }

    header > div {
        display: flex;
        align-items: center;
        gap: 10px;
    }

    header > nav {
        display: flex;
        align-items: center;
        justify-content: space-around;
    }

    header > nav > a {
        padding: 8px;
    }

    header > nav > a:hover {
        margin-bottom: -3px;
        border-bottom: 3px solid green;
    }

    .call-to-action {
        padding: 15px 30px;
        border-radius: 5px;
        background-color: green;
    }

    .call-to-action:hover {
        margin-bottom: unset;
        border-bottom: unset;
    }

    .active {
        margin-bottom: -3px;
        border-bottom: 3px solid green;
    }

</style>