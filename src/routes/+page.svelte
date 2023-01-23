<script lang="ts">
  import type { PageData } from "./$types";
  import ThemeSwitch from '$lib/ThemeSwitch/ThemeSwitch.svelte';

  export let data: PageData;
</script>

<svelte:head>
  <title>Home</title>
  <meta name="description" content="Svelte demo app" />
</svelte:head>
<ThemeSwitch />
<section>

  <ul>
    {#each data.contents as content}
      <li><a href="{content.id}">{content.title}</a></li>
    {/each}
  </ul>
</section>


<style lang="postcss">

</style>
