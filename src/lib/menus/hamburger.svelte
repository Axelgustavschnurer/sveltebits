<script>
    export let links = [
        {linkTitle: 'Link Ipsum', href: './'}, 
        {linkTitle: 'Link Ipsum', href: './'}, 
        {linkTitle: 'Link Ipsum', href: './'} 
    ]

    let activeLink

</script>

<div>
    <input type="checkbox">
    <svg viewBox="0 0 100 80" width="30" height="30">
        <rect y="0" width="100" height="10"></rect>
        <rect y="35" width="100" height="10"></rect>
        <rect y="70" width="100" height="10"></rect>
    </svg>
    <nav>
        {#each links as link, i}
            <a href={link.href}>{link.linkTitle}</a>
        {/each}
    </nav>
</div>

<style>

    :root {
        --hamburger-width: ;
    }

    div {
        /*
            Oh i see if you set a position on this div it means that the "nearest
            positioned ancestor" of the navbar is this div instead of the header. 
            This will break shit so don't do that. 
        */
        padding: 25px;
    }

    input[type="checkbox"] {
        width: 30px;
        height: 30px;
        margin: 0;
        padding: 0;
        cursor: pointer;
        
        /* Temp maybe (hopefully)*/
        position: absolute;
        opacity: 0;
    }

    input[type="checkbox"]:checked ~ nav {
        display: block;
    }

    nav {
        background-color: #fefefe;
        display: none;
        position: absolute;
        width: 100%;
        top: 100%;
        /* 
            Assuming that the menu is located inside an element containing a position of  
            absolute, fixed, relative or sticky the top: 100%; value will place the 
            navbar beneath the parent element. This means that it works as it should
            when placed in a parent element that is positioned. 
            Why is it like this? I don't know, this shit should not work but here is a link
            explaining it i think?: https://www.w3schools.com/cssref/pr_pos_top.php#:~:text=The%20top%20property%20affects%20the,of%20its%20nearest%20positioned%20ancestor.
        */
        /*
            Actually it kinda makes perfect sense, refer to comment on div styling above
        */
        left: 0;
    }

    nav > a {
        display: block;
        padding: 15px;
        border-bottom: 2px solid #ececec;
        text-decoration: unset;
        color: unset;
    }

    nav > a:hover {
        background-color: #ececec;
    }

    .active {
        border-bottom: 3px solid var(--color-accent);
    }

</style>