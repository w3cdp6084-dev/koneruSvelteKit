<script lang="ts">
  import type { PageData } from "./$types";
  import ThemeSwitch from '$lib/ThemeSwitch/ThemeSwitch.svelte';
  import { Card, Button, Toggle } from "flowbite-svelte";
  let vCard = false;
  export let data: PageData;
</script>

<svelte:head>
  <title>Home</title>
  <meta name="description" content="Svelte demo app" />
</svelte:head>

<ThemeSwitch />

<section>
  <ul class="lg:flex sm:block">
    {#each data.contents as content}
      <!-- <li class="cardWrap">
        <div>
          <img src={content.eyecatch?.url} alt="イメージ画像" />
        </div>
        <div>
          <a href="{content.id}">{content.title}</a>
        </div>
        <div>
          <a href="/">#カテゴリ</a>
        </div>
      </li> -->
      <div>
        <Card img={content.eyecatch?.url} reverse={vCard}>
          <a href="{content.id}" class="mb-2 text-2xl font-bold tracking-tight text-gray-900 dark:text-white">{content.title}</a><br>
          <a href="{content.id}" class="mb-3 font-normal text-gray-700 dark:text-gray-400 leading-tight">{content.category.name}</a>
        </Card>
      </div>
    {/each}
  </ul>
</section>


<style lang="postcss">

</style>
