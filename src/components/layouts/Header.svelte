<script>
    import { Hamburger } from 'svelte-hamburgers';
    import Menu from './Menu.svelte';
    let open;
</script>

<header class="l-header">
	<div class="hamburgerWrap">
		<Hamburger
			bind:open
			--color="black" />
	</div>
	<Menu bind:open />

</header>
<style lang="postcss">
	.l-header {
		position: relative;
		height: auto;
	}
	/* .hamburgerWrap{
		top: 0;
		right: 0;
	} */
</style>