<script>
    import "../app.css";
    import Header from '../components/layouts/Header.svelte';
    import Footer from '../components/layouts/Footer.svelte';
</script>

<Header />

<div class="l-content">
    <slot />
</div>
<Footer />