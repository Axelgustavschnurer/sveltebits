<script>
    export let links = [
      { linkTitle: 'Read More', href: './' },
      [
        { linkTitle: 'Read More', href: './' },
        { linkTitle: 'Read More', href: './' },
        { linkTitle: 'Read More', href: './' }
      ],
      { linkTitle: 'Read More', href: './' },
      { linkTitle: 'Read More', href: './' }
    ];
  
    let showNestedLinks = false;
  
    function toggleNestedLinks() {
      showNestedLinks = !showNestedLinks;
    }
  </script>
  
  <ul>
    {#each links as link}
      {#if Array.isArray(link)}
        <li>
          <button on:click={toggleNestedLinks}>
            {link[0].linkTitle}
          </button>
          {#if showNestedLinks}
            <ul>
              {#each link as nestedLink}
                <li>
                  <a href={nestedLink.href}>{nestedLink.linkTitle}</a>
                </li>
              {/each}
            </ul>
          {/if}
        </li>
      {:else}
        <li>
          <a href={link.href}>{link.linkTitle}</a>
        </li>
      {/if}
    {/each}
  </ul>
  
  <style>
    ul {
      list-style: none;
      padding: 0;
    }
  
    li {
      margin-bottom: 10px;
    }
  </style>
  