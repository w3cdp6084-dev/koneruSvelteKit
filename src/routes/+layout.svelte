<script>
    import "../app.css";
    import Header from '../components/layouts/Header.svelte';
    import Footer from '../components/layouts/Footer.svelte';
</script>

<div class="wrap">
    <Header />
        <div class="l-content">
            <slot />
        </div>
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
        background-color: aqua;
    }
</style>