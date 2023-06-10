<script>

</script>

<div>
    <input type="checkbox">
    <nav>
        <a href="./">Test</a>
        <a href="./">Test</a>
        <a href="./">Test</a>
        <a href="./">Test</a>
        <a href="./">Test</a>
        <a href="./">Test</a>
    </nav>
</div>

<style>

    div {
        padding: 25px;
    }

    input[type="checkbox"] {
        width: 25px;
        height: 25px;
        margin: 0;
        padding: 0;
        cursor: pointer;
    }

    input[type="checkbox"]:checked + nav {
        display: block;
    }

    nav {
        display: none;
        position: absolute;
        /* Why does top 100% work? */
        width: 100%;
        top: 100%;
        left: 0;
    }

    nav > a {
        display: block;
        padding: 15px;
        background-color: #fefefe;
    }

    nav > a:hover {
        background-color: #ececec;
    }

</style>