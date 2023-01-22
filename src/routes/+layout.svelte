<script>
    import "../app.css";
    import Header from '../components/layouts/Header.svelte';
    import Footer from '../components/layouts/Footer.svelte';
    import { Hamburger } from 'svelte-hamburgers';
    import Menu from '../components/layouts/Menu.svelte';

    let open;
</script>

<Header />
<Hamburger
    bind:open
    --color="black" />

<Menu bind:open />
<div class="l-content">
    <slot />
</div>
<Footer />