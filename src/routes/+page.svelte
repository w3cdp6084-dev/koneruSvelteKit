<script lang="ts">
  import type { PageData } from "./$types";
  import { Card} from "flowbite-svelte";

  export let data: PageData;
  
</script>

<svelte:head>
  <title>Home</title>
  <meta name="description" content="Svelte demo app" />
</svelte:head>



<section>
  <ul class="lg:grid sm:block gap-10 grid-cols-3">
    {#each data.contents as content}
      <li class="list">
        <Card img={content.eyecatch?.url} class="item max-w-lg">
          <a href="{content.id}" class="mb-2 text-2xl font-bold tracking-tight text-gray-900 dark:text-white">{content.title}</a><br>
          <a href="{content.id}" class="mb-3 font-normal text-gray-700 dark:text-gray-400 leading-tight">{content.category.name}</a>
          <p class="mb-2 text-gray-700 dark:text-gray-400 leading-tight">{content.publishedAt}</p>
        </Card>
      </li>
    {/each}
  </ul>
</section>


<style lang="postcss">

</style>
