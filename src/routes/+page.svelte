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
  <ul class="flex">
    {#each data.contents as content}
      <li class="cardWrap">
        <div>
          <img src={content.eyecatch?.url} alt="イメージ画像" />
        </div>
        <div>
          <a href="{content.id}">{content.title}</a>
        </div>
        <div>
          <a href="/">#カテゴリ</a>
        </div>
      </li>
      
    {/each}
  </ul>
</section>


<style lang="postcss">

</style>
