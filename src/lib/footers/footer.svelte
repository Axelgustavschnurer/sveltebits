<script>
    export let columns = [
        {'Column 1': ['link1', 'link2', 'link3']},
        {'Column 2': ['link1', 'link2', 'link3']},
        {'Column 3': ['link1', 'link2', 'link3']}
    ]
</script>

<footer>
    {#each columns as column}
        {#each Object.entries(column) as [title, links]}
            <div>
                <h3>{title}</h3>
                {#each links as link}
                    <a href="./">{link}</a>
                {/each}
            </div>
        {/each}
    {/each}
</footer>

<style>
    :root {
        --background-color: white;
        --color-main: black;
        --color-second: white;
        --color-accent: cornflowerblue;
    }

    * {
        font-family: Arial, Helvetica, sans-serif;
    }

    footer {
        border-top: 3px solid var(--color-accent);
        padding: 25px;
        display: flex;
        justify-content: space-around;
    }

    footer > div {
        display: flex;
        flex-direction: column;
    }

    a {
        text-decoration: unset;
        color: unset;
    }

    footer > div > a {
        padding: 8px 0;
        width: fit-content;
    }

    footer > div > a:hover {
        margin-bottom: -3px;
        border-bottom: 3px solid var(--color-accent);
    }

</style>