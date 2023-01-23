<script lang="ts">
  import type { PageData } from "./$types";

  export let data: PageData;
</script>

<svelte:head>
  <title>Home</title>
  <meta name="description" content="Svelte demo app" />
</svelte:head>

<section>

  <ul>
    {#each data.contents as content}
      <li><a href="{content.id}">{content.title}</a></li>
    {/each}
  </ul>
</section>


<style lang="postcss">
    :global(html) {
      background-color: theme(colors.gray.100);
    }
</style>
