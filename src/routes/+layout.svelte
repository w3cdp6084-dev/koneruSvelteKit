<script>
    import "../app.css";
    import Header from '../components/layouts/Header.svelte';
    import Footer from '../components/layouts/Footer.svelte';
</script>

<div class="wrap">
    <Header />
        <main class="l-content mt-24">
            <slot />
        </main>
    <Footer />
</div>
<style lang="postcss">
    .wrap{
        position: relative;
        min-height: 100vh;
        width: 100%;
    }
    .l-content{
        position: relative;
        max-width: 1280px;
        margin: 0 auto;
    }
</style>