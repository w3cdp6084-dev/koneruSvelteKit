<script>
    import { Hamburger } from 'svelte-hamburgers';
    import Menu from './Menu.svelte';
    let open;
</script>

<header class="l-header">
	<Hamburger
    	bind:open
    	--color="black" />
	<Menu bind:open />
</header>