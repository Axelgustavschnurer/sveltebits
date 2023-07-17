<script>
    import Hamburger2 from "../../lib/menus/hamburger2.svelte";
    import Nav from "../../lib/navigation/nav.svelte"
</script>

<header style="position: sticky; top: 0; display: flex; flex-direction: row-reverse;">
    <Hamburger2
        --hamburger2-py=100px
        --hamburger2-px=25px
        --hamburger2-height=100vh
        --hamburger2-nav-left=initial
    />
</header>

<main style="height: 200vh;">
    <Nav 
        caption="Test"
        links={[
          {linkTitle:"test", href:'./'}, 
          {linkTitle:"test", href:'./'},
          {linkTitle:"Test", href:'./'}
        ]}
        --nav-nav-flex-direction="row"
        --gap=100px
    />
</main>
